# UlpUpdateReservationInRegistry

- ea: `0x140150f5c`
- end: `0x140151147`
- name: `UlpUpdateReservationInRegistry`
- size: `491`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x1401502e0`
- `0x1401505d8`

## callees

- `0x1400424b0`
- `0x140150f5c`
- `0x140167840`

## import_xrefs

- `ntoskrnl!ZwDeleteValueKey` at `0x140151101`
- `ntoskrnl!ZwDeleteValueKey` at `0x14015110f`
- `ntoskrnl!ZwDeleteValueKey` at `0x140151101`
- `ntoskrnl!ZwDeleteValueKey` at `0x14015110f`
- `ntoskrnl!ZwSetValueKey` at `0x1401510e3`
- `ntoskrnl!ZwSetValueKey` at `0x1401510e3`
- `ntoskrnl!wcschr` at `0x140151015`
- `ntoskrnl!wcschr` at `0x140151034`
- `ntoskrnl!wcschr` at `0x14015104f`
- `ntoskrnl!wcschr` at `0x14015106f`
- `ntoskrnl!wcschr` at `0x140151015`
- `ntoskrnl!wcschr` at `0x140151034`
- `ntoskrnl!wcschr` at `0x14015104f`
- `ntoskrnl!wcschr` at `0x14015106f`
- `ntoskrnl!ExAllocatePool3` at `0x140150fcc`
- `ntoskrnl!ExAllocatePool3` at `0x140150fcc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140151127`
- `ntoskrnl!ExFreePoolWithTag` at `0x140151127`

## pseudocode

```c
__int64 __fastcall UlpUpdateReservationInRegistry(__int64 a1, char a2, __int64 a3, void *a4, ULONG DataSize)
{
  NTSTATUS inited; // ebx
  size_t v10; // r14
  wchar_t *Pool3; // rax
  wchar_t *v12; // rdi
  wchar_t *v13; // rax
  wchar_t *v14; // rax
  wchar_t *v15; // rax
  wchar_t *v16; // rsi
  wchar_t *v17; // rax
  wchar_t *v18; // rdx
  void *v19; // rcx
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-58h] BYREF

  ValueName = 0;
  if ( !*(_QWORD *)(a1 + 1400) )
    return (unsigned int)-1073741816;
  if ( *(_DWORD *)(a3 + 4) == 2 )
  {
    v10 = 2LL * *(unsigned __int16 *)(a3 + 56) + 2;
    Pool3 = (wchar_t *)ExAllocatePool3(258, v10, 1280666709, UxLowPriorityPool, 1);
    v12 = Pool3;
    if ( !Pool3 )
      return (unsigned int)-1073741670;
    inited = 0;
    memmove(Pool3, *(const void **)(a3 + 8), v10);
    v13 = v12 + 7;
    if ( (v12[7] == 91 || v12[8] == 91) && (v13 = wcschr(v12 + 7, 0x5Du)) == 0
      || (v14 = wcschr(v13, 0x3Au)) == 0
      || (v15 = wcschr(v14 + 1, 0x3Au), (v16 = v15) == 0)
      || (v17 = wcschr(v15, 0x2Fu)) == 0 )
    {
LABEL_23:
      ExFreePoolWithTag(v12, 0);
      return (unsigned int)inited;
    }
    while ( *v17 )
      *v16++ = *v17++;
    *v16 = 0;
    v18 = v12;
  }
  else
  {
    v18 = *(wchar_t **)(a3 + 8);
    v12 = 0;
  }
  inited = UlInitUnicodeStringEx(&ValueName, v18);
  if ( inited >= 0 )
  {
    v19 = *(void **)(a1 + 1400);
    if ( a2 )
    {
      inited = ZwSetValueKey(v19, &ValueName, 0, 3u, a4, DataSize);
      if ( inited < 0 )
        ZwDeleteValueKey(*(HANDLE *)(a1 + 1400), &ValueName);
    }
    else
    {
      inited = ZwDeleteValueKey(v19, &ValueName);
    }
  }
  if ( v12 )
    goto LABEL_23;
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x140150f5c  push    rbx
0x140150f5e  push    rbp
0x140150f5f  push    rsi
0x140150f60  push    rdi
0x140150f61  push    r12
0x140150f63  push    r13
0x140150f65  push    r14
0x140150f67  push    r15
0x140150f69  sub     rsp, 48h
0x140150f6d  xor     r13d, r13d
0x140150f70  xorps   xmm0, xmm0
0x140150f73  mov     r12, r9
0x140150f76  mov     rsi, r8
0x140150f79  mov     r15b, dl
0x140150f7c  mov     rbp, rcx
0x140150f7f  movups  xmmword ptr [rsp+88h+ValueName.Length], xmm0
0x140150f84  cmp     [rcx+578h], r13
0x140150f8b  jnz     short loc_140150F97
0x140150f8d  mov     ebx, 0C0000008h
0x140150f92  jmp     loc_140151133
0x140150f97  cmp     dword ptr [r8+4], 2
0x140150f9c  jnz     loc_1401510A2
0x140150fa2  movzx   eax, word ptr [r8+38h]
0x140150fa7  lea     r9, UxLowPriorityPool
0x140150fae  mov     r8d, 4C556C55h
0x140150fb4  mov     dword ptr [rsp+88h+Data], 1
0x140150fbc  mov     ecx, 102h
0x140150fc1  lea     r14, ds:2[rax*2]
0x140150fc9  mov     rdx, r14
0x140150fcc  call    cs:__imp_ExAllocatePool3
0x140150fd3  nop     dword ptr [rax+rax+00h]
0x140150fd8  mov     rdi, rax
0x140150fdb  test    rax, rax
0x140150fde  jnz     short loc_140150FEA
0x140150fe0  mov     ebx, 0C000009Ah
0x140150fe5  jmp     loc_140151133
0x140150fea  mov     rdx, [rsi+8]; Src
0x140150fee  mov     r8, r14; Size
0x140150ff1  mov     rcx, rdi; void *
0x140150ff4  mov     ebx, r13d
0x140150ff7  call    memmove
0x140150ffc  lea     rax, [rdi+0Eh]
0x140151000  cmp     word ptr [rax], 5Bh ; '['
0x140151004  jz      short loc_14015100D
0x140151006  cmp     word ptr [rax+2], 5Bh ; '['
0x14015100b  jnz     short loc_14015102A
0x14015100d  mov     edx, 5Dh ; ']'; Ch
0x140151012  mov     rcx, rax; Str
0x140151015  call    cs:__imp_wcschr
0x14015101c  nop     dword ptr [rax+rax+00h]
0x140151021  test    rax, rax
0x140151024  jz      loc_140151122
0x14015102a  mov     esi, 3Ah ; ':'
0x14015102f  mov     rcx, rax; Str
0x140151032  mov     edx, esi; Ch
0x140151034  call    cs:__imp_wcschr
0x14015103b  nop     dword ptr [rax+rax+00h]
0x140151040  test    rax, rax
0x140151043  jz      loc_140151122
0x140151049  mov     edx, esi; Ch
0x14015104b  lea     rcx, [rax+2]; Str
0x14015104f  call    cs:__imp_wcschr
0x140151056  nop     dword ptr [rax+rax+00h]
0x14015105b  mov     rsi, rax
0x14015105e  test    rax, rax
0x140151061  jz      loc_140151122
0x140151067  mov     edx, 2Fh ; '/'; Ch
0x14015106c  mov     rcx, rax; Str
0x14015106f  call    cs:__imp_wcschr
0x140151076  nop     dword ptr [rax+rax+00h]
0x14015107b  test    rax, rax
0x14015107e  jz      loc_140151122
0x140151084  jmp     short loc_140151091
0x140151086  mov     [rsi], cx
0x140151089  lea     rax, [rax+2]
0x14015108d  add     rsi, 2
0x140151091  movzx   ecx, word ptr [rax]
0x140151094  test    cx, cx
0x140151097  jnz     short loc_140151086
0x140151099  mov     [rsi], r13w
0x14015109d  mov     rdx, rdi
0x1401510a0  jmp     short loc_1401510A9
0x1401510a2  mov     rdx, [r8+8]
0x1401510a6  mov     rdi, r13
0x1401510a9  lea     rcx, [rsp+88h+ValueName]
0x1401510ae  call    UlInitUnicodeStringEx
0x1401510b3  mov     ebx, eax
0x1401510b5  test    eax, eax
0x1401510b7  js      short loc_14015111D
0x1401510b9  mov     rcx, [rbp+578h]; KeyHandle
0x1401510c0  lea     rdx, [rsp+88h+ValueName]; ValueName
0x1401510c5  test    r15b, r15b
0x1401510c8  jz      short loc_14015110F
0x1401510ca  mov     eax, [rsp+88h+arg_20]
0x1401510d1  mov     r9d, 3; Type
0x1401510d7  mov     [rsp+88h+DataSize], eax; DataSize
0x1401510db  xor     r8d, r8d; TitleIndex
0x1401510de  mov     [rsp+88h+Data], r12; Data
0x1401510e3  call    cs:__imp_ZwSetValueKey
0x1401510ea  nop     dword ptr [rax+rax+00h]
0x1401510ef  mov     ebx, eax
0x1401510f1  test    eax, eax
0x1401510f3  jns     short loc_14015111D
0x1401510f5  mov     rcx, [rbp+578h]; KeyHandle
0x1401510fc  lea     rdx, [rsp+88h+ValueName]; ValueName
0x140151101  call    cs:__imp_ZwDeleteValueKey
0x140151108  nop     dword ptr [rax+rax+00h]
0x14015110d  jmp     short loc_14015111D
0x14015110f  call    cs:__imp_ZwDeleteValueKey
0x140151116  nop     dword ptr [rax+rax+00h]
0x14015111b  mov     ebx, eax
0x14015111d  test    rdi, rdi
0x140151120  jz      short loc_140151133
0x140151122  xor     edx, edx; Tag
0x140151124  mov     rcx, rdi; P
0x140151127  call    cs:__imp_ExFreePoolWithTag
0x14015112e  nop     dword ptr [rax+rax+00h]
0x140151133  mov     eax, ebx
0x140151135  add     rsp, 48h
0x140151139  pop     r15
0x14015113b  pop     r14
0x14015113d  pop     r13
0x14015113f  pop     r12
0x140151141  pop     rdi
0x140151142  pop     rsi
0x140151143  pop     rbp
0x140151144  pop     rbx
0x140151145  retn
```
