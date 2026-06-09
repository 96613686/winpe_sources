# GetCallerAuthenticatedUserSid(ushort * *)

- ea: `0x18000cbd8`
- end: `0x18000ccc5`
- name: `?GetCallerAuthenticatedUserSid@@YAJPEAPEAG@Z`
- size: `237`
- prototype: `int(unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180019060`
- `0x180019410`

## callees

- `0x18000cbd8`
- `0x18000e180`
- `0x180011b98`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc9c`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x18000cc24`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x18000cc24`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetCallerAuthenticatedUserSid(HLOCAL *a1)
{
  int CurrentUserSid; // edi
  __int64 v4; // rdx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  bool v7; // [rsp+30h] [rbp+8h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp+10h] BYREF

  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x926,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmapi\\src\\omadmapi.cpp",
      (const char *)0x80070057LL,
      v5);
    return 2147942487LL;
  }
  *a1 = 0;
  hMem = 0;
  CurrentUserSid = DmGetCurrentUserSid((unsigned __int16 **)&hMem);
  if ( CurrentUserSid < 0 )
  {
    v4 = 2346;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmapi\\src\\omadmapi.cpp",
      (const char *)(unsigned int)CurrentUserSid,
      v5);
    if ( hMem )
      LocalFree(hMem);
    return (unsigned int)CurrentUserSid;
  }
  v7 = 0;
  CurrentUserSid = IsWellKnownSid((const unsigned __int16 *)hMem, &v7);
  if ( CurrentUserSid < 0 )
  {
    v4 = 2349;
    goto LABEL_5;
  }
  if ( v7 )
  {
    if ( hMem )
      LocalFree(hMem);
    return 1;
  }
  else
  {
    *a1 = hMem;
    return 0;
  }
}

```

## disassembly

```asm
0x18000cbd8  mov     [rsp+arg_10], rbx
0x18000cbdd  push    rdi; int
0x18000cbde  sub     rsp, 20h
0x18000cbe2  mov     rbx, rcx
0x18000cbe5  test    rcx, rcx
0x18000cbe8  jnz     short loc_18000CC0F
0x18000cbea  mov     rcx, [rsp+28h]; this
0x18000cbef  mov     ebx, 80070057h
0x18000cbf4  mov     r9d, ebx; char *
0x18000cbf7  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\dm\\omadm\\omadmapi"...
0x18000cbfe  mov     edx, 926h; void *
0x18000cc03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cc08  mov     eax, ebx
0x18000cc0a  jmp     loc_18000CCB9
0x18000cc0f  mov     qword ptr [rcx], 0
0x18000cc16  mov     [rsp+28h+hMem], 0
0x18000cc1f  lea     rcx, [rsp+28h+hMem]
0x18000cc24  call    cs:__imp_?DmGetCurrentUserSid@@YAJPEAPEAG@Z; DmGetCurrentUserSid(ushort * *)
0x18000cc2b  nop     dword ptr [rax+rax+00h]
0x18000cc30  mov     edi, eax
0x18000cc32  test    eax, eax
0x18000cc34  jns     short loc_18000CC6A
0x18000cc36  mov     edx, 92Ah; void *
0x18000cc3b  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\dm\\omadm\\omadmapi"...
0x18000cc42  mov     r9d, edi; char *
0x18000cc45  mov     rcx, [rsp+28h]; this
0x18000cc4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cc4f  nop
0x18000cc50  mov     rcx, [rsp+28h+hMem]; hMem
0x18000cc55  test    rcx, rcx
0x18000cc58  jz      short loc_18000CC66
0x18000cc5a  call    cs:__imp_LocalFree
0x18000cc61  nop     dword ptr [rax+rax+00h]
0x18000cc66  mov     eax, edi
0x18000cc68  jmp     short loc_18000CCB9
0x18000cc6a  mov     [rsp+28h+arg_0], 0
0x18000cc6f  lea     rdx, [rsp+28h+arg_0]; bool *
0x18000cc74  mov     rcx, [rsp+28h+hMem]; unsigned __int16 *
0x18000cc79  call    ?IsWellKnownSid@@YAJPEBGPEA_N@Z; IsWellKnownSid(ushort const *,bool *)
0x18000cc7e  mov     edi, eax
0x18000cc80  test    eax, eax
0x18000cc82  jns     short loc_18000CC8B
0x18000cc84  mov     edx, 92Dh
0x18000cc89  jmp     short loc_18000CC3B
0x18000cc8b  cmp     [rsp+28h+arg_0], 0
0x18000cc90  jz      short loc_18000CCAF
0x18000cc92  mov     rcx, [rsp+28h+hMem]; hMem
0x18000cc97  test    rcx, rcx
0x18000cc9a  jz      short loc_18000CCA8
0x18000cc9c  call    cs:__imp_LocalFree
0x18000cca3  nop     dword ptr [rax+rax+00h]
0x18000cca8  mov     eax, 1
0x18000ccad  jmp     short loc_18000CCB9
0x18000ccaf  mov     rax, [rsp+28h+hMem]
0x18000ccb4  mov     [rbx], rax
0x18000ccb7  xor     eax, eax
0x18000ccb9  mov     rbx, [rsp+28h+arg_10]
0x18000ccbe  add     rsp, 20h
0x18000ccc2  pop     rdi
0x18000ccc3  retn
```
