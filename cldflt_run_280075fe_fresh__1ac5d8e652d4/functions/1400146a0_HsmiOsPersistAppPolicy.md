# HsmiOsPersistAppPolicy

- ea: `0x1400146a0`
- end: `0x1400147fb`
- name: `HsmiOsPersistAppPolicy`
- size: `347`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14001266c`

## callees

- `0x1400146a0`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x14001472b`
- `ntoskrnl!ZwSetValueKey` at `0x140014771`
- `ntoskrnl!ZwSetValueKey` at `0x1400147b2`
- `ntoskrnl!ZwSetValueKey` at `0x1400147e0`
- `ntoskrnl!ZwSetValueKey` at `0x14001472b`
- `ntoskrnl!ZwSetValueKey` at `0x140014771`
- `ntoskrnl!ZwSetValueKey` at `0x1400147b2`
- `ntoskrnl!ZwSetValueKey` at `0x1400147e0`

## string_xrefs

- `0x1400146b1`: `ImagePath`

## pseudocode

```c
int __fastcall HsmiOsPersistAppPolicy(HANDLE KeyHandle, __int64 a2, __int64 a3, __int64 a4)
{
  void *Data; // rax
  int result; // eax
  void *v9; // rcx
  void *v10; // rcx
  ULONG DataSize; // [rsp+28h] [rbp-58h]
  int v12; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+38h] [rbp-48h] BYREF
  struct _UNICODE_STRING v14; // [rsp+48h] [rbp-38h] BYREF
  struct _UNICODE_STRING v15; // [rsp+58h] [rbp-28h] BYREF
  struct _UNICODE_STRING v16; // [rsp+68h] [rbp-18h] BYREF

  v12 = 1;
  ValueName.Buffer = L"ImagePath";
  *(_QWORD *)&ValueName.Length = 1310738;
  v14.Buffer = L"PackageName";
  *(_QWORD *)&v14.Length = 1572886;
  v15.Buffer = L"AppName";
  *(_QWORD *)&v15.Length = 1048590;
  v16.Buffer = L"Enabled";
  DataSize = *(unsigned __int16 *)(a2 + 2);
  Data = *(void **)(a2 + 8);
  *(_QWORD *)&v16.Length = 1048590;
  result = ZwSetValueKey(KeyHandle, &ValueName, 0, 1u, Data, DataSize);
  if ( result >= 0 )
  {
    if ( !a3
      || (v9 = *(void **)(a3 + 8)) == 0
      || !*(_WORD *)a3
      || (result = ZwSetValueKey(KeyHandle, &v14, 0, 1u, v9, *(unsigned __int16 *)(a3 + 2)), result >= 0) )
    {
      if ( !a4 )
        return ZwSetValueKey(KeyHandle, &v16, 0, 4u, &v12, 4u);
      v10 = *(void **)(a4 + 8);
      if ( !v10 )
        return ZwSetValueKey(KeyHandle, &v16, 0, 4u, &v12, 4u);
      if ( !*(_WORD *)a4 )
        return ZwSetValueKey(KeyHandle, &v16, 0, 4u, &v12, 4u);
      result = ZwSetValueKey(KeyHandle, &v15, 0, 1u, v10, *(unsigned __int16 *)(a4 + 2));
      if ( result >= 0 )
        return ZwSetValueKey(KeyHandle, &v16, 0, 4u, &v12, 4u);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400146a0  push    rbp
0x1400146a2  push    rbx
0x1400146a3  push    rsi
0x1400146a4  push    rdi
0x1400146a5  push    r14
0x1400146a7  mov     rbp, rsp
0x1400146aa  sub     rsp, 80h
0x1400146b1  lea     rax, aImagepath; "ImagePath"
0x1400146b8  mov     [rbp+var_50], 1
0x1400146bf  mov     [rbp+ValueName.Buffer], rax
0x1400146c3  mov     rbx, r9
0x1400146c6  lea     rax, aPackagename; "PackageName"
0x1400146cd  mov     qword ptr [rbp+ValueName.Length], 140012h
0x1400146d5  mov     [rbp+var_38.Buffer], rax
0x1400146d9  mov     rdi, r8
0x1400146dc  lea     rax, aAppname; "AppName"
0x1400146e3  mov     qword ptr [rbp+var_38.Length], 180016h
0x1400146eb  mov     [rbp+var_28.Buffer], rax
0x1400146ef  mov     r9d, 1; Type
0x1400146f5  lea     rax, aEnabled; "Enabled"
0x1400146fc  mov     qword ptr [rbp+var_28.Length], 10000Eh
0x140014704  mov     [rbp+var_18.Buffer], rax
0x140014708  xor     r8d, r8d; TitleIndex
0x14001470b  movzx   eax, word ptr [rdx+2]
0x14001470f  mov     rsi, rcx
0x140014712  mov     [rsp+80h+DataSize], eax; DataSize
0x140014716  mov     rax, [rdx+8]
0x14001471a  lea     rdx, [rbp+ValueName]; ValueName
0x14001471e  mov     [rsp+80h+Data], rax; Data
0x140014723  mov     qword ptr [rbp+var_18.Length], 10000Eh
0x14001472b  call    cs:__imp_ZwSetValueKey
0x140014732  nop     dword ptr [rax+rax+00h]
0x140014737  xor     r14d, r14d
0x14001473a  test    eax, eax
0x14001473c  js      loc_1400147EC
0x140014742  test    rdi, rdi
0x140014745  jz      short loc_140014781
0x140014747  mov     rcx, [rdi+8]
0x14001474b  test    rcx, rcx
0x14001474e  jz      short loc_140014781
0x140014750  cmp     [rdi], r14w
0x140014754  jz      short loc_140014781
0x140014756  movzx   eax, word ptr [rdi+2]
0x14001475a  lea     r9d, [r14+1]; Type
0x14001475e  mov     [rsp+80h+DataSize], eax; DataSize
0x140014762  lea     rdx, [rbp+var_38]; ValueName
0x140014766  mov     [rsp+80h+Data], rcx; Data
0x14001476b  xor     r8d, r8d; TitleIndex
0x14001476e  mov     rcx, rsi; KeyHandle
0x140014771  call    cs:__imp_ZwSetValueKey
0x140014778  nop     dword ptr [rax+rax+00h]
0x14001477d  test    eax, eax
0x14001477f  js      short loc_1400147EC
0x140014781  test    rbx, rbx
0x140014784  jz      short loc_1400147C2
0x140014786  mov     rcx, [rbx+8]
0x14001478a  test    rcx, rcx
0x14001478d  jz      short loc_1400147C2
0x14001478f  cmp     [rbx], r14w
0x140014793  jz      short loc_1400147C2
0x140014795  movzx   eax, word ptr [rbx+2]
0x140014799  lea     rdx, [rbp+var_28]; ValueName
0x14001479d  mov     [rsp+80h+DataSize], eax; DataSize
0x1400147a1  mov     r9d, 1; Type
0x1400147a7  mov     [rsp+80h+Data], rcx; Data
0x1400147ac  xor     r8d, r8d; TitleIndex
0x1400147af  mov     rcx, rsi; KeyHandle
0x1400147b2  call    cs:__imp_ZwSetValueKey
0x1400147b9  nop     dword ptr [rax+rax+00h]
0x1400147be  test    eax, eax
0x1400147c0  js      short loc_1400147EC
0x1400147c2  mov     r9d, 4; Type
0x1400147c8  lea     rax, [rbp+var_50]
0x1400147cc  mov     [rsp+80h+DataSize], r9d; DataSize
0x1400147d1  lea     rdx, [rbp+var_18]; ValueName
0x1400147d5  xor     r8d, r8d; TitleIndex
0x1400147d8  mov     [rsp+80h+Data], rax; Data
0x1400147dd  mov     rcx, rsi; KeyHandle
0x1400147e0  call    cs:__imp_ZwSetValueKey
0x1400147e7  nop     dword ptr [rax+rax+00h]
0x1400147ec  add     rsp, 80h
0x1400147f3  pop     r14
0x1400147f5  pop     rdi
0x1400147f6  pop     rsi
0x1400147f7  pop     rbx
0x1400147f8  pop     rbp
0x1400147f9  retn
```
