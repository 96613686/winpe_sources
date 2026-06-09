# DeleteMMAuthMethods

- ea: `0x18001bcb4`
- end: `0x18001be3d`
- name: `DeleteMMAuthMethods`
- size: `393`
- prototype: `__int64 __fastcall(__int64, __int64, __int128 *)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x180004910`
- `0x180010e50`
- `0x1800280f4`
- `0x1800281dc`

## callees

- `0x18000e510`
- `0x18001bc28`
- `0x18001bcb4`
- `0x18001be44`
- `0x18001cc18`
- `0x18001cc50`
- `0x1800446d4`
- `0x18004d090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bce3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bce3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bdd8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bde9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bdd8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bde9`

## pseudocode

```c
__int64 __fastcall DeleteMMAuthMethods(__int64 a1, __int64 a2, __int128 *a3)
{
  __int64 v3; // rcx
  __int64 MMAuthMethods; // rax
  _QWORD *v5; // rbx
  unsigned int v6; // edi
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  unsigned int v10; // eax
  __int128 v12; // [rsp+30h] [rbp-38h] BYREF
  __int128 v13; // [rsp+40h] [rbp-28h] BYREF

  v13 = *a3;
  EnterCriticalSection(&gcSPDSection);
  v12 = v13;
  MMAuthMethods = FindMMAuthMethods(v3, &v12);
  v5 = (_QWORD *)MMAuthMethods;
  if ( !MMAuthMethods )
  {
    v6 = 13011;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_15;
      v8 = 33;
LABEL_5:
      v9 = v6;
      goto LABEL_14;
    }
    goto LABEL_18;
  }
  if ( *(_DWORD *)(MMAuthMethods + 20) )
  {
    v6 = 13012;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_15;
      v8 = 34;
      goto LABEL_5;
    }
LABEL_18:
    LeaveCriticalSection(&gcSPDSection);
    return v6;
  }
  LipsApiIkeAuthDelete(MMAuthMethods);
  v10 = DeleteIniMMAuthMethods(v5);
  v6 = v10;
  if ( v10 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_15;
      v8 = 35;
      v9 = v10;
LABEL_14:
      WPP_SF_d(v7[2], v8, WPP_a85e1ba878913aef4692d4169706eb40_Traceguids, v9);
      v7 = WPP_GLOBAL_Control;
LABEL_15:
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x10) != 0 )
        WPP_SF__guid_D(v7[2], 37, WPP_a85e1ba878913aef4692d4169706eb40_Traceguids, &v13, v6);
      goto LABEL_18;
    }
    goto LABEL_18;
  }
  LeaveCriticalSection(&gcSPDSection);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_a85e1ba878913aef4692d4169706eb40_Traceguids, &v13);
  return 0;
}

```

## disassembly

```asm
0x18001bcb4  mov     [rsp+arg_0], rbx
0x18001bcb9  mov     [rsp+arg_8], rsi
0x18001bcbe  push    rdi
0x18001bcbf  sub     rsp, 60h
0x18001bcc3  mov     rax, cs:__security_cookie
0x18001bcca  xor     rax, rsp
0x18001bccd  mov     [rsp+68h+var_18], rax
0x18001bcd2  movaps  xmm0, xmmword ptr [r8]
0x18001bcd6  lea     rcx, gcSPDSection; lpCriticalSection
0x18001bcdd  movdqa  [rsp+68h+var_28], xmm0
0x18001bce3  call    cs:__imp_EnterCriticalSection
0x18001bce9  movaps  xmm0, [rsp+68h+var_28]
0x18001bcee  lea     rdx, [rsp+68h+var_38]
0x18001bcf3  movdqa  [rsp+68h+var_38], xmm0
0x18001bcf9  call    FindMMAuthMethods
0x18001bcfe  lea     rsi, WPP_a85e1ba878913aef4692d4169706eb40_Traceguids
0x18001bd05  mov     rbx, rax
0x18001bd08  test    rax, rax
0x18001bd0b  jnz     short loc_18001BD37
0x18001bd0d  mov     edi, 32D3h
0x18001bd12  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd19  lea     rbx, WPP_GLOBAL_Control
0x18001bd20  cmp     rcx, rbx
0x18001bd23  jz      loc_18001BDD1
0x18001bd29  test    byte ptr [rcx+1Ch], 10h
0x18001bd2d  jz      short loc_18001BDAC
0x18001bd2f  lea     edx, [rax+21h]
0x18001bd32  mov     r9d, edi
0x18001bd35  jmp     short loc_18001BD99
0x18001bd37  cmp     dword ptr [rax+14h], 0
0x18001bd3b  jz      short loc_18001BD62
0x18001bd3d  mov     edi, 32D4h
0x18001bd42  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd49  lea     rbx, WPP_GLOBAL_Control
0x18001bd50  cmp     rcx, rbx
0x18001bd53  jz      short loc_18001BDD1
0x18001bd55  test    byte ptr [rcx+1Ch], 10h
0x18001bd59  jz      short loc_18001BDAC
0x18001bd5b  mov     edx, 22h ; '"'
0x18001bd60  jmp     short loc_18001BD32
0x18001bd62  mov     rcx, rbx
0x18001bd65  call    LipsApiIkeAuthDelete
0x18001bd6a  mov     rcx, rbx; lpMem
0x18001bd6d  call    DeleteIniMMAuthMethods
0x18001bd72  mov     edi, eax
0x18001bd74  test    eax, eax
0x18001bd76  jz      short loc_18001BDE2
0x18001bd78  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd7f  lea     rbx, WPP_GLOBAL_Control
0x18001bd86  cmp     rcx, rbx
0x18001bd89  jz      short loc_18001BDD1
0x18001bd8b  test    byte ptr [rcx+1Ch], 10h
0x18001bd8f  jz      short loc_18001BDAC
0x18001bd91  mov     edx, 23h ; '#'
0x18001bd96  mov     r9d, eax
0x18001bd99  mov     rcx, [rcx+10h]
0x18001bd9d  mov     r8, rsi
0x18001bda0  call    WPP_SF_d
0x18001bda5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bdac  cmp     rcx, rbx
0x18001bdaf  jz      short loc_18001BDD1
0x18001bdb1  test    byte ptr [rcx+1Ch], 10h
0x18001bdb5  jz      short loc_18001BDD1
0x18001bdb7  mov     rcx, [rcx+10h]
0x18001bdbb  lea     r9, [rsp+68h+var_28]
0x18001bdc0  mov     edx, 25h ; '%'
0x18001bdc5  mov     [rsp+68h+var_48], edi
0x18001bdc9  mov     r8, rsi
0x18001bdcc  call    WPP_SF__guid_D
0x18001bdd1  lea     rcx, gcSPDSection; lpCriticalSection
0x18001bdd8  call    cs:__imp_LeaveCriticalSection
0x18001bdde  mov     eax, edi
0x18001bde0  jmp     short loc_18001BE20
0x18001bde2  lea     rcx, gcSPDSection; lpCriticalSection
0x18001bde9  call    cs:__imp_LeaveCriticalSection
0x18001bdef  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bdf6  lea     rbx, WPP_GLOBAL_Control
0x18001bdfd  cmp     rcx, rbx
0x18001be00  jz      short loc_18001BE1E
0x18001be02  test    byte ptr [rcx+1Ch], 4
0x18001be06  jz      short loc_18001BE1E
0x18001be08  mov     rcx, [rcx+10h]
0x18001be0c  lea     r9, [rsp+68h+var_28]
0x18001be11  mov     edx, 24h ; '$'
0x18001be16  mov     r8, rsi
0x18001be19  call    WPP_SF__guid_
0x18001be1e  xor     eax, eax
0x18001be20  mov     rcx, [rsp+68h+var_18]
0x18001be25  xor     rcx, rsp; StackCookie
0x18001be28  call    __security_check_cookie
0x18001be2d  mov     rbx, [rsp+68h+arg_0]
0x18001be32  mov     rsi, [rsp+68h+arg_8]
0x18001be37  add     rsp, 60h
0x18001be3b  pop     rdi
0x18001be3c  retn
```
