# HsmiOsPersistAppPolicy

- ea: `0x140014720`
- end: `0x14001487b`
- name: `HsmiOsPersistAppPolicy`
- size: `347`
- prototype: `int __fastcall(HANDLE KeyHandle, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400126ec`

## callees

- `0x140014720`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x1400147ab`
- `ntoskrnl!ZwSetValueKey` at `0x1400147f1`
- `ntoskrnl!ZwSetValueKey` at `0x140014832`
- `ntoskrnl!ZwSetValueKey` at `0x140014860`
- `ntoskrnl!ZwSetValueKey` at `0x1400147ab`
- `ntoskrnl!ZwSetValueKey` at `0x1400147f1`
- `ntoskrnl!ZwSetValueKey` at `0x140014832`
- `ntoskrnl!ZwSetValueKey` at `0x140014860`

## string_xrefs

- `0x140014731`: `ImagePath`

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
0x140014720  push    rbp
0x140014722  push    rbx
0x140014723  push    rsi
0x140014724  push    rdi
0x140014725  push    r14
0x140014727  mov     rbp, rsp
0x14001472a  sub     rsp, 80h
0x140014731  lea     rax, aImagepath; "ImagePath"
0x140014738  mov     [rbp+var_50], 1
0x14001473f  mov     [rbp+ValueName.Buffer], rax
0x140014743  mov     rbx, r9
0x140014746  lea     rax, aPackagename; "PackageName"
0x14001474d  mov     qword ptr [rbp+ValueName.Length], 140012h
0x140014755  mov     [rbp+var_38.Buffer], rax
0x140014759  mov     rdi, r8
0x14001475c  lea     rax, aAppname; "AppName"
0x140014763  mov     qword ptr [rbp+var_38.Length], 180016h
0x14001476b  mov     [rbp+var_28.Buffer], rax
0x14001476f  mov     r9d, 1; Type
0x140014775  lea     rax, aEnabled; "Enabled"
0x14001477c  mov     qword ptr [rbp+var_28.Length], 10000Eh
0x140014784  mov     [rbp+var_18.Buffer], rax
0x140014788  xor     r8d, r8d; TitleIndex
0x14001478b  movzx   eax, word ptr [rdx+2]
0x14001478f  mov     rsi, rcx
0x140014792  mov     [rsp+80h+DataSize], eax; DataSize
0x140014796  mov     rax, [rdx+8]
0x14001479a  lea     rdx, [rbp+ValueName]; ValueName
0x14001479e  mov     [rsp+80h+Data], rax; Data
0x1400147a3  mov     qword ptr [rbp+var_18.Length], 10000Eh
0x1400147ab  call    cs:__imp_ZwSetValueKey
0x1400147b2  nop     dword ptr [rax+rax+00h]
0x1400147b7  xor     r14d, r14d
0x1400147ba  test    eax, eax
0x1400147bc  js      loc_14001486C
0x1400147c2  test    rdi, rdi
0x1400147c5  jz      short loc_140014801
0x1400147c7  mov     rcx, [rdi+8]
0x1400147cb  test    rcx, rcx
0x1400147ce  jz      short loc_140014801
0x1400147d0  cmp     [rdi], r14w
0x1400147d4  jz      short loc_140014801
0x1400147d6  movzx   eax, word ptr [rdi+2]
0x1400147da  lea     r9d, [r14+1]; Type
0x1400147de  mov     [rsp+80h+DataSize], eax; DataSize
0x1400147e2  lea     rdx, [rbp+var_38]; ValueName
0x1400147e6  mov     [rsp+80h+Data], rcx; Data
0x1400147eb  xor     r8d, r8d; TitleIndex
0x1400147ee  mov     rcx, rsi; KeyHandle
0x1400147f1  call    cs:__imp_ZwSetValueKey
0x1400147f8  nop     dword ptr [rax+rax+00h]
0x1400147fd  test    eax, eax
0x1400147ff  js      short loc_14001486C
0x140014801  test    rbx, rbx
0x140014804  jz      short loc_140014842
0x140014806  mov     rcx, [rbx+8]
0x14001480a  test    rcx, rcx
0x14001480d  jz      short loc_140014842
0x14001480f  cmp     [rbx], r14w
0x140014813  jz      short loc_140014842
0x140014815  movzx   eax, word ptr [rbx+2]
0x140014819  lea     rdx, [rbp+var_28]; ValueName
0x14001481d  mov     [rsp+80h+DataSize], eax; DataSize
0x140014821  mov     r9d, 1; Type
0x140014827  mov     [rsp+80h+Data], rcx; Data
0x14001482c  xor     r8d, r8d; TitleIndex
0x14001482f  mov     rcx, rsi; KeyHandle
0x140014832  call    cs:__imp_ZwSetValueKey
0x140014839  nop     dword ptr [rax+rax+00h]
0x14001483e  test    eax, eax
0x140014840  js      short loc_14001486C
0x140014842  mov     r9d, 4; Type
0x140014848  lea     rax, [rbp+var_50]
0x14001484c  mov     [rsp+80h+DataSize], r9d; DataSize
0x140014851  lea     rdx, [rbp+var_18]; ValueName
0x140014855  xor     r8d, r8d; TitleIndex
0x140014858  mov     [rsp+80h+Data], rax; Data
0x14001485d  mov     rcx, rsi; KeyHandle
0x140014860  call    cs:__imp_ZwSetValueKey
0x140014867  nop     dword ptr [rax+rax+00h]
0x14001486c  add     rsp, 80h
0x140014873  pop     r14
0x140014875  pop     rdi
0x140014876  pop     rsi
0x140014877  pop     rbx
0x140014878  pop     rbp
0x140014879  retn
```
