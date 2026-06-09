# CheckAppAccessRightBasedOnCapability

- ea: `0x1800172ac`
- end: `0x180017395`
- name: `CheckAppAccessRightBasedOnCapability`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008858`

## callees

- `0x18000d094`
- `0x1800172ac`
- `0x1800173ec`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017375`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017375`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180017311`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180017311`

## pseudocode

```c
__int64 __fastcall CheckAppAccessRightBasedOnCapability(
        void *a1,
        int a2,
        const wchar_t *a3,
        __int64 a4,
        char a5,
        __int64 a6)
{
  int AppSid; // ebx
  __int64 v10; // rbp
  unsigned int i; // edi
  int v12; // eax
  int v13; // edx
  wchar_t *String1; // [rsp+20h] [rbp-38h] BYREF

  String1 = 0;
  a5 = 0;
  AppSid = GetAppSid(a1, &String1);
  if ( AppSid >= 0 )
  {
    v10 = a6;
    for ( i = 0; i < 4; ++i )
    {
      if ( (unsigned int)CapabilityCheck(a1, *(_QWORD *)(v10 + 16LL * i), &a5) )
      {
        AppSid = 0;
      }
      else if ( a5 && (a2 & *(_DWORD *)(v10 + 16LL * i + 8)) != 0 && (a2 & *(_DWORD *)(v10 + 16LL * i + 12)) == 0 )
      {
        AppSid = 0;
        goto LABEL_16;
      }
    }
    if ( a4 )
    {
      AppSid = -2146893808;
    }
    else
    {
      v12 = wcsicmp(String1, a3);
      v13 = AppSid;
      if ( v12 )
        v13 = -2146893808;
      AppSid = v13;
    }
  }
LABEL_16:
  if ( String1 )
    LocalFree(String1);
  return (unsigned int)AppSid;
}

```

## disassembly

```asm
0x1800172ac  mov     rax, rsp
0x1800172af  mov     [rax+8], rbx
0x1800172b3  mov     [rax+10h], rbp
0x1800172b7  mov     [rax+18h], r8
0x1800172bb  push    rdi
0x1800172bc  push    r12
0x1800172be  push    r13
0x1800172c0  push    r14
0x1800172c2  push    r15
0x1800172c4  sub     rsp, 30h
0x1800172c8  mov     r15d, edx
0x1800172cb  mov     qword ptr [rax-38h], 0
0x1800172d3  lea     rdx, [rax-38h]
0x1800172d7  mov     byte ptr [rax+28h], 0
0x1800172db  mov     r12, r9
0x1800172de  mov     r13, rcx
0x1800172e1  call    GetAppSid
0x1800172e6  mov     ebx, eax
0x1800172e8  test    eax, eax
0x1800172ea  js      short loc_180017368
0x1800172ec  mov     rbp, [rsp+58h+arg_28]
0x1800172f4  xor     edi, edi
0x1800172f6  cmp     edi, 4
0x1800172f9  jnb     short loc_18001733F
0x1800172fb  mov     r14d, edi
0x1800172fe  lea     r8, [rsp+58h+arg_20]
0x180017306  add     r14, r14
0x180017309  mov     rcx, r13
0x18001730c  mov     rdx, [rbp+r14*8+0]
0x180017311  call    cs:__imp_CapabilityCheck
0x180017317  test    eax, eax
0x180017319  jz      short loc_18001731F
0x18001731b  xor     ebx, ebx
0x18001731d  jmp     short loc_180017337
0x18001731f  cmp     [rsp+58h+arg_20], 0
0x180017327  jz      short loc_180017337
0x180017329  test    [rbp+r14*8+8], r15d
0x18001732e  jz      short loc_180017337
0x180017330  test    [rbp+r14*8+0Ch], r15d
0x180017335  jz      short loc_18001733B
0x180017337  inc     edi
0x180017339  jmp     short loc_1800172F6
0x18001733b  xor     ebx, ebx
0x18001733d  jmp     short loc_180017368
0x18001733f  test    r12, r12
0x180017342  jz      short loc_18001734B
0x180017344  mov     ebx, 80090010h
0x180017349  jmp     short loc_180017368
0x18001734b  mov     rdx, [rsp+58h+String2]; String2
0x180017350  mov     rcx, [rsp+58h+String1]; String1
0x180017355  call    _wcsicmp
0x18001735a  mov     edx, ebx
0x18001735c  test    eax, eax
0x18001735e  mov     ebx, 80090010h
0x180017363  cmovnz  edx, ebx
0x180017366  mov     ebx, edx
0x180017368  cmp     [rsp+58h+String1], 0
0x18001736e  jz      short loc_18001737B
0x180017370  mov     rcx, [rsp+58h+String1]; hMem
0x180017375  call    cs:__imp_LocalFree
0x18001737b  mov     rbp, [rsp+58h+arg_8]
0x180017380  mov     eax, ebx
0x180017382  mov     rbx, [rsp+58h+arg_0]
0x180017387  add     rsp, 30h
0x18001738b  pop     r15
0x18001738d  pop     r14
0x18001738f  pop     r13
0x180017391  pop     r12
0x180017393  pop     rdi
0x180017394  retn
```
