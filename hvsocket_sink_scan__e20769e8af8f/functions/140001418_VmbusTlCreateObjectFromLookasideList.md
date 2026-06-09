# VmbusTlCreateObjectFromLookasideList

- ea: `0x140001418`
- end: `0x140001500`
- name: `VmbusTlCreateObjectFromLookasideList`
- size: `232`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400085c8`
- `0x140019b70`

## callees

- `0x140001418`
- `0x140001714`
- `0x140009cf8`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140001465`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140001465`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400014dc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400014dc`

## string_xrefs

- `0x140001440`: `LookAsideList invalid.`
- `0x14000144f`: `VmbusTlCreateObjectFromLookasideList`
- `0x1400014ca`: `VmbusTlCreateObjectFromLookasideList`

## pseudocode

```c
__int64 __fastcall VmbusTlCreateObjectFromLookasideList(int a1, struct _NPAGED_LOOKASIDE_LIST *a2, int **a3)
{
  unsigned int v6; // ebx
  const char *v7; // r9
  __int64 v8; // rdx
  __int64 result; // rax
  int *v10; // rax
  int *v11; // rbx
  int v12; // eax
  unsigned int v13; // esi

  if ( a2->L.Size < 0x68 )
  {
    v6 = -1073741789;
    if ( (unsigned int)dword_140013058 <= 2 )
      return v6;
    v7 = "LookAsideList invalid.";
    v8 = 163;
LABEL_4:
    HvsocketTraceError("VmbusTlCreateObjectFromLookasideList", v8, v6, v7);
    return v6;
  }
  v10 = (int *)ExAllocateFromNPagedLookasideList(a2);
  v11 = v10;
  if ( !v10 )
  {
    v6 = -1073741801;
    if ( (unsigned int)dword_140013058 <= 2 )
      return v6;
    v7 = "No list passed in.";
    v8 = 172;
    goto LABEL_4;
  }
  v12 = VmbusTlInitializeObject(a1, a2->L.Size, 2, v10);
  v13 = v12;
  if ( v12 >= 0 )
  {
    *((_QWORD *)v11 + 12) = a2;
    result = 0;
    *a3 = v11;
  }
  else
  {
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceError("VmbusTlCreateObjectFromLookasideList", 182, (unsigned int)v12, "Failed to initialize object.");
    ExFreeToNPagedLookasideList(a2, v11);
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x140001418  push    rbx
0x14000141a  push    rsi
0x14000141b  push    rdi
0x14000141c  push    r14
0x14000141e  sub     rsp, 28h
0x140001422  cmp     dword ptr [rdx+2Ch], 68h ; 'h'
0x140001426  mov     r14, r8
0x140001429  mov     rdi, rdx
0x14000142c  mov     esi, ecx
0x14000142e  jnb     short loc_140001462
0x140001430  mov     ecx, cs:dword_140013058
0x140001436  mov     ebx, 0C0000023h
0x14000143b  cmp     ecx, 2
0x14000143e  jbe     short loc_14000145B
0x140001440  lea     r9, aLookasidelistI; "LookAsideList invalid."
0x140001447  mov     edx, 0A3h
0x14000144c  mov     r8d, ebx
0x14000144f  lea     rcx, aVmbustlcreateo_0; "VmbusTlCreateObjectFromLookasideList"
0x140001456  call    HvsocketTraceError
0x14000145b  mov     eax, ebx
0x14000145d  jmp     loc_1400014F5
0x140001462  mov     rcx, rdi; Lookaside
0x140001465  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000146c  nop     dword ptr [rax+rax+00h]
0x140001471  mov     rbx, rax
0x140001474  test    rax, rax
0x140001477  jnz     short loc_140001497
0x140001479  mov     ecx, cs:dword_140013058
0x14000147f  mov     ebx, 0C0000017h
0x140001484  cmp     ecx, 2
0x140001487  jbe     short loc_14000145B
0x140001489  lea     r9, aNoListPassedIn; "No list passed in."
0x140001490  mov     edx, 0ACh
0x140001495  jmp     short loc_14000144C
0x140001497  mov     edx, [rdi+2Ch]
0x14000149a  mov     r9, rbx
0x14000149d  mov     r8d, 2
0x1400014a3  mov     ecx, esi
0x1400014a5  call    VmbusTlInitializeObject
0x1400014aa  mov     esi, eax
0x1400014ac  test    eax, eax
0x1400014ae  jns     short loc_1400014EC
0x1400014b0  mov     ecx, cs:dword_140013058
0x1400014b6  cmp     ecx, 2
0x1400014b9  jbe     short loc_1400014D6
0x1400014bb  lea     r9, aFailedToInitia_0; "Failed to initialize object."
0x1400014c2  mov     r8d, eax
0x1400014c5  mov     edx, 0B6h
0x1400014ca  lea     rcx, aVmbustlcreateo_0; "VmbusTlCreateObjectFromLookasideList"
0x1400014d1  call    HvsocketTraceError
0x1400014d6  mov     rdx, rbx; Entry
0x1400014d9  mov     rcx, rdi; Lookaside
0x1400014dc  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400014e3  nop     dword ptr [rax+rax+00h]
0x1400014e8  mov     eax, esi
0x1400014ea  jmp     short loc_1400014F5
0x1400014ec  mov     [rbx+60h], rdi
0x1400014f0  xor     eax, eax
0x1400014f2  mov     [r14], rbx
0x1400014f5  add     rsp, 28h
0x1400014f9  pop     r14
0x1400014fb  pop     rdi
0x1400014fc  pop     rsi
0x1400014fd  pop     rbx
0x1400014fe  retn
```
