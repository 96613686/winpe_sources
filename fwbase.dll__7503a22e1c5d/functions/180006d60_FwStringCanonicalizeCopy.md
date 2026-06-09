# FwStringCanonicalizeCopy

- ea: `0x180006d60`
- end: `0x180006f3c`
- name: `FwStringCanonicalizeCopy`
- size: `476`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x180004840`
- `0x180004870`
- `0x180006d60`
- `0x180006f50`
- `0x18000ccd4`
- `0x18001e1d0`
- `0x18001eb54`
- `0x18002f674`

## import_xrefs

- `ntdll!RtlCanonicalizeDomainName` at `0x180006ded`
- `ntdll!RtlCanonicalizeDomainName` at `0x180006ded`
- `ntdll!RtlInitUnicodeString` at `0x180006dda`
- `ntdll!RtlInitUnicodeString` at `0x180006dda`
- `ntdll!RtlFreeUnicodeString` at `0x180006e57`
- `ntdll!RtlFreeUnicodeString` at `0x180006e57`

## pseudocode

```c
__int64 __fastcall FwStringCanonicalizeCopy(const WCHAR *a1, _QWORD *a2)
{
  unsigned __int64 v2; // rax
  const WCHAR *v4; // rdx
  unsigned int v5; // esi
  NTSTATUS v6; // eax
  int v7; // eax
  __int64 v8; // rdx
  unsigned int v9; // r14d
  size_t v10; // rbp
  _DWORD *v11; // rax
  _DWORD *v12; // rbx
  _QWORD *v13; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF

  v2 = -1;
  DestinationString = 0;
  UnicodeString = 0;
  do
    ++v2;
  while ( a1[v2] );
  if ( v2 < 2 )
  {
    v4 = a1 + 1;
    if ( *a1 == 46 )
    {
LABEL_15:
      v5 = 1;
      goto LABEL_7;
    }
  }
  else if ( *a1 == 46 )
  {
    v4 = a1 + 1;
    if ( a1[1] == 46 )
    {
      v4 = a1 + 2;
      v5 = 2;
      goto LABEL_7;
    }
    goto LABEL_15;
  }
  v5 = 0;
  v4 = a1;
LABEL_7:
  RtlInitUnicodeString(&DestinationString, v4);
  v6 = RtlCanonicalizeDomainName(&UnicodeString, &DestinationString, 0);
  v7 = FwNtStatusToHResult(v6);
  v9 = v7;
  if ( v7 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_12;
    v15 = 45;
    v16 = (unsigned int)v7;
    goto LABEL_26;
  }
  if ( v5 )
    v10 = UnicodeString.Length + 2LL * (v5 + 1);
  else
    v10 = UnicodeString.Length + 2LL;
  v11 = (_DWORD *)FwAlloc(v10, v8);
  v12 = v11;
  if ( !v11 )
  {
    v9 = -2147024882;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_12;
    v15 = 46;
    v16 = 2147942414LL;
LABEL_26:
    WPP_SF_d(v13[2], v15, WPP_b26c8f9d1741323f65697860432a8e18_Traceguids, v16);
LABEL_12:
    FwFree(0);
    goto LABEL_13;
  }
  memset_0(v11, 0, v10);
  if ( v5 == 2 )
  {
    *v12 = 3014702;
  }
  else if ( v5 == 1 )
  {
    *(_WORD *)v12 = 46;
  }
  memcpy_0((char *)v12 + 2 * v5, UnicodeString.Buffer, UnicodeString.Length);
  *a2 = v12;
LABEL_13:
  RtlFreeUnicodeString(&UnicodeString);
  return v9;
}

```

## disassembly

```asm
0x180006d60  mov     [rsp+arg_10], rbx
0x180006d65  mov     [rsp+arg_18], rbp
0x180006d6a  push    rsi
0x180006d6b  push    rdi
0x180006d6c  push    r12
0x180006d6e  push    r14
0x180006d70  push    r15
0x180006d72  sub     rsp, 50h
0x180006d76  mov     rax, cs:__security_cookie
0x180006d7d  xor     rax, rsp
0x180006d80  mov     [rsp+78h+var_38], rax
0x180006d85  xorps   xmm0, xmm0
0x180006d88  xorps   xmm1, xmm1
0x180006d8b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006d8f  mov     r15, rdx
0x180006d92  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x180006d97  xor     r12d, r12d
0x180006d9a  movups  xmmword ptr [rsp+78h+UnicodeString.Length], xmm1
0x180006d9f  inc     rax
0x180006da2  cmp     [rcx+rax*2], r12w
0x180006da7  jnz     short loc_180006D9F
0x180006da9  mov     edi, 2Eh ; '.'
0x180006dae  cmp     rax, 2
0x180006db2  jb      loc_180006E86
0x180006db8  cmp     [rcx], di
0x180006dbb  jnz     loc_180006EBF
0x180006dc1  lea     rdx, [rcx+2]
0x180006dc5  cmp     [rdx], di
0x180006dc8  jnz     loc_180006E8F
0x180006dce  lea     rdx, [rcx+4]; SourceString
0x180006dd2  lea     esi, [rdi-2Ch]
0x180006dd5  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x180006dda  call    cs:__imp_RtlInitUnicodeString
0x180006de0  xor     r8d, r8d
0x180006de3  lea     rdx, [rsp+78h+DestinationString]
0x180006de8  lea     rcx, [rsp+78h+UnicodeString]
0x180006ded  call    cs:__imp_RtlCanonicalizeDomainName
0x180006df3  mov     ecx, eax
0x180006df5  call    FwNtStatusToHResult
0x180006dfa  mov     r14d, eax
0x180006dfd  test    eax, eax
0x180006dff  js      loc_180006E99
0x180006e05  test    esi, esi
0x180006e07  jz      loc_180006F00
0x180006e0d  movzx   eax, [rsp+78h+UnicodeString.Length]
0x180006e12  lea     ecx, [rsi+1]
0x180006e15  lea     rbp, [rax+rcx*2]
0x180006e19  mov     rcx, rbp
0x180006e1c  call    FwAlloc
0x180006e21  mov     rbx, rax
0x180006e24  test    rax, rax
0x180006e27  jnz     loc_180006ECA
0x180006e2d  mov     r14d, 8007000Eh
0x180006e33  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e3a  lea     rdx, WPP_GLOBAL_Control
0x180006e41  cmp     rcx, rdx
0x180006e44  jnz     loc_180006F0E
0x180006e4a  mov     rcx, rbx
0x180006e4d  call    FwFree
0x180006e52  lea     rcx, [rsp+78h+UnicodeString]; UnicodeString
0x180006e57  call    cs:__imp_RtlFreeUnicodeString
0x180006e5d  mov     eax, r14d
0x180006e60  mov     rcx, [rsp+78h+var_38]
0x180006e65  xor     rcx, rsp; StackCookie
0x180006e68  call    __security_check_cookie
0x180006e6d  lea     r11, [rsp+78h+var_28]
0x180006e72  mov     rbx, [r11+40h]
0x180006e76  mov     rbp, [r11+48h]
0x180006e7a  mov     rsp, r11
0x180006e7d  pop     r15
0x180006e7f  pop     r14
0x180006e81  pop     r12
0x180006e83  pop     rdi
0x180006e84  pop     rsi
0x180006e85  retn
0x180006e86  lea     rdx, [rcx+2]
0x180006e8a  cmp     [rcx], di
0x180006e8d  jnz     short loc_180006EBF
0x180006e8f  mov     esi, 1
0x180006e94  jmp     loc_180006DD5
0x180006e99  mov     rbx, r12
0x180006e9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ea3  lea     rdx, WPP_GLOBAL_Control
0x180006eaa  cmp     rcx, rdx
0x180006ead  jz      short loc_180006E4A
0x180006eaf  test    byte ptr [rcx+1Ch], 1
0x180006eb3  jz      short loc_180006E4A
0x180006eb5  mov     edx, 2Dh ; '-'
0x180006eba  mov     r9d, eax
0x180006ebd  jmp     short loc_180006F1D
0x180006ebf  mov     esi, r12d
0x180006ec2  mov     rdx, rcx
0x180006ec5  jmp     loc_180006DD5
0x180006eca  mov     r8, rbp; Size
0x180006ecd  xor     edx, edx; Val
0x180006ecf  mov     rcx, rbx; void *
0x180006ed2  call    memset_0
0x180006ed7  cmp     esi, 2
0x180006eda  jnz     short loc_180006F32
0x180006edc  mov     dword ptr [rbx], 2E002Eh
0x180006ee2  movzx   r8d, [rsp+78h+UnicodeString.Length]; Size
0x180006ee8  mov     rdx, [rsp+78h+UnicodeString.Buffer]; Src
0x180006eed  mov     eax, esi
0x180006eef  lea     rcx, [rbx+rax*2]; void *
0x180006ef3  call    memcpy_0
0x180006ef8  mov     [r15], rbx
0x180006efb  jmp     loc_180006E52
0x180006f00  movzx   ebp, [rsp+78h+UnicodeString.Length]
0x180006f05  add     rbp, 2
0x180006f09  jmp     loc_180006E19
0x180006f0e  test    byte ptr [rcx+1Ch], 1
0x180006f12  jz      loc_180006E4A
0x180006f18  mov     edx, edi
0x180006f1a  mov     r9d, r14d
0x180006f1d  mov     rcx, [rcx+10h]
0x180006f21  lea     r8, WPP_b26c8f9d1741323f65697860432a8e18_Traceguids
0x180006f28  call    WPP_SF_d
0x180006f2d  jmp     loc_180006E4A
0x180006f32  cmp     esi, 1
0x180006f35  jnz     short loc_180006EE2
0x180006f37  mov     [rbx], di
0x180006f3a  jmp     short loc_180006EE2
```
