# DeleteTunnelFilter

- ea: `0x180031ad0`
- end: `0x180031c2a`
- name: `DeleteTunnelFilter`
- size: `346`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x1800116c0`
- `0x180016150`
- `0x18002ffe0`
- `0x1800300b4`

## callees

- `0x18000e510`
- `0x1800175dc`
- `0x18001cc18`
- `0x18001cc50`
- `0x180031888`
- `0x180031994`
- `0x180031ad0`
- `0x180032ae4`
- `0x18004d090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031b90`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031b90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031c1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031c1d`

## pseudocode

```c
__int64 __fastcall DeleteTunnelFilter(__int64 a1)
{
  __int64 v2; // rdi
  _QWORD *v3; // rcx
  unsigned int v5; // eax
  __int64 v6; // rcx
  unsigned int v7; // edi
  __int64 v8; // rcx
  __int128 v9; // [rsp+30h] [rbp-28h] BYREF

  if ( !a1 )
    return 87;
  v2 = *(_QWORD *)(a1 + 8);
  v9 = *(_OWORD *)(a1 + 16);
  if ( !v2 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids, 87);
        v3 = WPP_GLOBAL_Control;
      }
      if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x10) != 0 )
        WPP_SF__guid_D(v3[2], 43, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids, &v9, 87);
    }
    return 87;
  }
  EnterCriticalSection(&gcSPDSection);
  DeactivateTunnelFilterFromLips(v2);
  v5 = *(_DWORD *)(v2 + 236);
  if ( v5 <= 1 )
  {
    v7 = DeleteIniTnFilter((_QWORD *)v2);
    RemoveTnFilterHandle(a1);
    SPDApiBufferFree(v8);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids, &v9);
  }
  else
  {
    *(_DWORD *)(v2 + 244) = 1;
    *(_DWORD *)(v2 + 236) = v5 - 1;
    RemoveTnFilterHandle(a1);
    SPDApiBufferFree(v6);
    v7 = 0;
  }
  LeaveCriticalSection(&gcSPDSection);
  return v7;
}

```

## disassembly

```asm
0x180031ad0  mov     [rsp+arg_8], rbx
0x180031ad5  push    rdi
0x180031ad6  sub     rsp, 50h
0x180031ada  mov     rax, cs:__security_cookie
0x180031ae1  xor     rax, rsp
0x180031ae4  mov     [rsp+58h+var_18], rax
0x180031ae9  mov     rbx, rcx
0x180031aec  test    rcx, rcx
0x180031aef  jz      short loc_180031B6C
0x180031af1  movups  xmm0, xmmword ptr [rcx+10h]
0x180031af5  mov     rdi, [rcx+8]
0x180031af9  movdqu  [rsp+58h+var_28], xmm0
0x180031aff  test    rdi, rdi
0x180031b02  jnz     loc_180031B89
0x180031b08  mov     rcx, cs:WPP_GLOBAL_Control
0x180031b0f  lea     rbx, WPP_GLOBAL_Control
0x180031b16  cmp     rcx, rbx
0x180031b19  jz      short loc_180031B6C
0x180031b1b  test    byte ptr [rcx+1Ch], 10h
0x180031b1f  jz      short loc_180031B3F
0x180031b21  mov     rcx, [rcx+10h]
0x180031b25  lea     edx, [rdi+29h]
0x180031b28  lea     r9d, [rdi+57h]
0x180031b2c  lea     r8, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids
0x180031b33  call    WPP_SF_d
0x180031b38  mov     rcx, cs:WPP_GLOBAL_Control
0x180031b3f  cmp     rcx, rbx
0x180031b42  jz      short loc_180031B6C
0x180031b44  test    byte ptr [rcx+1Ch], 10h
0x180031b48  jz      short loc_180031B6C
0x180031b4a  mov     rcx, [rcx+10h]
0x180031b4e  lea     r9, [rsp+58h+var_28]
0x180031b53  mov     edx, 2Bh ; '+'
0x180031b58  mov     [rsp+58h+var_38], 57h ; 'W'
0x180031b60  lea     r8, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids
0x180031b67  call    WPP_SF__guid_D
0x180031b6c  mov     eax, 57h ; 'W'
0x180031b71  mov     rcx, [rsp+58h+var_18]
0x180031b76  xor     rcx, rsp; StackCookie
0x180031b79  call    __security_check_cookie
0x180031b7e  mov     rbx, [rsp+58h+arg_8]
0x180031b83  add     rsp, 50h
0x180031b87  pop     rdi
0x180031b88  retn
0x180031b89  lea     rcx, gcSPDSection; lpCriticalSection
0x180031b90  call    cs:__imp_EnterCriticalSection
0x180031b96  mov     rcx, rdi
0x180031b99  call    DeactivateTunnelFilterFromLips
0x180031b9e  mov     eax, [rdi+0ECh]
0x180031ba4  cmp     eax, 1
0x180031ba7  jbe     short loc_180031BCC
0x180031ba9  dec     eax
0x180031bab  mov     dword ptr [rdi+0F4h], 1
0x180031bb5  mov     rcx, rbx
0x180031bb8  mov     [rdi+0ECh], eax
0x180031bbe  call    RemoveTnFilterHandle
0x180031bc3  call    SPDApiBufferFree
0x180031bc8  xor     edi, edi
0x180031bca  jmp     short loc_180031C16
0x180031bcc  mov     rcx, rdi; lpMem
0x180031bcf  call    DeleteIniTnFilter
0x180031bd4  mov     rcx, rbx
0x180031bd7  mov     edi, eax
0x180031bd9  call    RemoveTnFilterHandle
0x180031bde  call    SPDApiBufferFree
0x180031be3  mov     rcx, cs:WPP_GLOBAL_Control
0x180031bea  lea     rbx, WPP_GLOBAL_Control
0x180031bf1  cmp     rcx, rbx
0x180031bf4  jz      short loc_180031C16
0x180031bf6  test    byte ptr [rcx+1Ch], 4
0x180031bfa  jz      short loc_180031C16
0x180031bfc  mov     rcx, [rcx+10h]
0x180031c00  lea     r9, [rsp+58h+var_28]
0x180031c05  mov     edx, 2Ah ; '*'
0x180031c0a  lea     r8, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids
0x180031c11  call    WPP_SF__guid_
0x180031c16  lea     rcx, gcSPDSection; lpCriticalSection
0x180031c1d  call    cs:__imp_LeaveCriticalSection
0x180031c23  mov     eax, edi
0x180031c25  jmp     loc_180031B71
```
