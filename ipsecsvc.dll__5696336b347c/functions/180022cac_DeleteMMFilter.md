# DeleteMMFilter

- ea: `0x180022cac`
- end: `0x180022ec8`
- name: `DeleteMMFilter`
- size: `540`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x18000fd60`
- `0x180010f40`
- `0x18002902c`
- `0x18002912c`

## callees

- `0x18000e510`
- `0x1800175dc`
- `0x18001cc18`
- `0x18001cc50`
- `0x180022b94`
- `0x180022cac`
- `0x18002402c`
- `0x18004482c`
- `0x18004d090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022ce9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022ce9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022d92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022e59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022e77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022d92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022e59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022e77`

## pseudocode

```c
__int64 __fastcall DeleteMMFilter(__int64 a1)
{
  __int64 v3; // rbx
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  unsigned int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v10; // eax
  _QWORD *v11; // rcx
  __int64 v12; // rcx
  __int128 v13; // [rsp+30h] [rbp-28h] BYREF

  v13 = 0;
  if ( !a1 )
    return 87;
  EnterCriticalSection(&gcSPDSection);
  v3 = *(_QWORD *)(a1 + 8);
  if ( !v3 )
  {
    v4 = 87;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids, 87);
        v5 = WPP_GLOBAL_Control;
      }
      if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x10) != 0 )
        WPP_SF_d(v5[2], 57, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids, 87);
    }
LABEL_23:
    LeaveCriticalSection(&gcSPDSection);
    return v4;
  }
  v6 = *(_DWORD *)(v3 + 124);
  if ( v6 <= 1 )
  {
    v8 = *(_QWORD *)(a1 + 8);
    v13 = *(_OWORD *)(v3 + 4);
    v9 = LipsApiIkeFilterDelete(v8);
    if ( v9
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF__guid_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids, &v13, v9);
    }
    v10 = DeleteIniMMFilter((_QWORD *)v3);
    v4 = v10;
    if ( v10 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids, v10);
          v11 = WPP_GLOBAL_Control;
        }
        if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x10) != 0 )
          WPP_SF__guid_D(v11[2], 56, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids, &v13, v4);
      }
      goto LABEL_23;
    }
    RemoveMMFilterHandle(a1);
    SPDApiBufferFree(v12);
    LeaveCriticalSection(&gcSPDSection);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids, &v13);
  }
  else
  {
    *(_DWORD *)(v3 + 132) = 1;
    *(_DWORD *)(v3 + 124) = v6 - 1;
    RemoveMMFilterHandle(a1);
    SPDApiBufferFree(v7);
    LeaveCriticalSection(&gcSPDSection);
  }
  return 0;
}

```

## disassembly

```asm
0x180022cac  mov     [rsp+arg_8], rbx
0x180022cb1  mov     [rsp+arg_10], rsi
0x180022cb6  push    rdi
0x180022cb7  sub     rsp, 50h
0x180022cbb  mov     rax, cs:__security_cookie
0x180022cc2  xor     rax, rsp
0x180022cc5  mov     [rsp+58h+var_18], rax
0x180022cca  xorps   xmm0, xmm0
0x180022ccd  mov     rsi, rcx
0x180022cd0  movups  [rsp+58h+var_28], xmm0
0x180022cd5  test    rcx, rcx
0x180022cd8  jnz     short loc_180022CE2
0x180022cda  lea     eax, [rcx+57h]
0x180022cdd  jmp     loc_180022EAB
0x180022ce2  lea     rcx, gcSPDSection; lpCriticalSection
0x180022ce9  call    cs:__imp_EnterCriticalSection
0x180022cef  mov     rbx, [rsi+8]
0x180022cf3  test    rbx, rbx
0x180022cf6  jnz     short loc_180022D67
0x180022cf8  mov     ebx, 57h ; 'W'
0x180022cfd  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d04  lea     rdi, WPP_GLOBAL_Control
0x180022d0b  cmp     rcx, rdi
0x180022d0e  jz      loc_180022E52
0x180022d14  test    byte ptr [rcx+1Ch], 10h
0x180022d18  jz      short loc_180022D37
0x180022d1a  mov     rcx, [rcx+10h]
0x180022d1e  lea     edx, [rbx-23h]
0x180022d21  mov     r9d, ebx
0x180022d24  lea     r8, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids
0x180022d2b  call    WPP_SF_d
0x180022d30  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d37  cmp     rcx, rdi
0x180022d3a  jz      loc_180022E52
0x180022d40  test    byte ptr [rcx+1Ch], 10h
0x180022d44  jz      loc_180022E52
0x180022d4a  mov     rcx, [rcx+10h]
0x180022d4e  lea     r8, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids
0x180022d55  mov     edx, 39h ; '9'
0x180022d5a  mov     r9d, ebx
0x180022d5d  call    WPP_SF_d
0x180022d62  jmp     loc_180022E52
0x180022d67  mov     eax, [rbx+7Ch]
0x180022d6a  cmp     eax, 1
0x180022d6d  jbe     short loc_180022D9D
0x180022d6f  dec     eax
0x180022d71  mov     dword ptr [rbx+84h], 1
0x180022d7b  mov     rcx, rsi
0x180022d7e  mov     [rbx+7Ch], eax
0x180022d81  call    RemoveMMFilterHandle
0x180022d86  call    SPDApiBufferFree
0x180022d8b  lea     rcx, gcSPDSection; lpCriticalSection
0x180022d92  call    cs:__imp_LeaveCriticalSection
0x180022d98  jmp     loc_180022EA9
0x180022d9d  movups  xmm0, xmmword ptr [rbx+4]
0x180022da1  mov     rcx, rbx
0x180022da4  movdqu  [rsp+58h+var_28], xmm0
0x180022daa  call    LipsApiIkeFilterDelete
0x180022daf  lea     rdi, WPP_GLOBAL_Control
0x180022db6  test    eax, eax
0x180022db8  jz      short loc_180022DEA
0x180022dba  mov     rcx, cs:WPP_GLOBAL_Control
0x180022dc1  cmp     rcx, rdi
0x180022dc4  jz      short loc_180022DEA
0x180022dc6  test    byte ptr [rcx+1Ch], 10h
0x180022dca  jz      short loc_180022DEA
0x180022dcc  mov     rcx, [rcx+10h]
0x180022dd0  lea     r9, [rsp+58h+var_28]
0x180022dd5  mov     edx, 35h ; '5'
0x180022dda  mov     [rsp+58h+var_38], eax
0x180022dde  lea     r8, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids
0x180022de5  call    WPP_SF__guid_D
0x180022dea  mov     rcx, rbx; lpMem
0x180022ded  call    DeleteIniMMFilter
0x180022df2  mov     ebx, eax
0x180022df4  test    eax, eax
0x180022df6  jz      short loc_180022E63
0x180022df8  mov     rcx, cs:WPP_GLOBAL_Control
0x180022dff  cmp     rcx, rdi
0x180022e02  jz      short loc_180022E52
0x180022e04  test    byte ptr [rcx+1Ch], 10h
0x180022e08  jz      short loc_180022E29
0x180022e0a  mov     rcx, [rcx+10h]
0x180022e0e  lea     r8, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids
0x180022e15  mov     edx, 36h ; '6'
0x180022e1a  mov     r9d, eax
0x180022e1d  call    WPP_SF_d
0x180022e22  mov     rcx, cs:WPP_GLOBAL_Control
0x180022e29  cmp     rcx, rdi
0x180022e2c  jz      short loc_180022E52
0x180022e2e  test    byte ptr [rcx+1Ch], 10h
0x180022e32  jz      short loc_180022E52
0x180022e34  mov     rcx, [rcx+10h]
0x180022e38  lea     r9, [rsp+58h+var_28]
0x180022e3d  mov     edx, 38h ; '8'
0x180022e42  mov     [rsp+58h+var_38], ebx
0x180022e46  lea     r8, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids
0x180022e4d  call    WPP_SF__guid_D
0x180022e52  lea     rcx, gcSPDSection; lpCriticalSection
0x180022e59  call    cs:__imp_LeaveCriticalSection
0x180022e5f  mov     eax, ebx
0x180022e61  jmp     short loc_180022EAB
0x180022e63  mov     rcx, rsi
0x180022e66  call    RemoveMMFilterHandle
0x180022e6b  call    SPDApiBufferFree
0x180022e70  lea     rcx, gcSPDSection; lpCriticalSection
0x180022e77  call    cs:__imp_LeaveCriticalSection
0x180022e7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022e84  cmp     rcx, rdi
0x180022e87  jz      short loc_180022EA9
0x180022e89  test    byte ptr [rcx+1Ch], 4
0x180022e8d  jz      short loc_180022EA9
0x180022e8f  mov     rcx, [rcx+10h]
0x180022e93  lea     r9, [rsp+58h+var_28]
0x180022e98  mov     edx, 37h ; '7'
0x180022e9d  lea     r8, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids
0x180022ea4  call    WPP_SF__guid_
0x180022ea9  xor     eax, eax
0x180022eab  mov     rcx, [rsp+58h+var_18]
0x180022eb0  xor     rcx, rsp; StackCookie
0x180022eb3  call    __security_check_cookie
0x180022eb8  mov     rbx, [rsp+58h+arg_8]
0x180022ebd  mov     rsi, [rsp+58h+arg_10]
0x180022ec2  add     rsp, 50h
0x180022ec6  pop     rdi
0x180022ec7  retn
```
