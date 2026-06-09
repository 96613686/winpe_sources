# PCW_NOTIFIER::Create(void * *,_UNICODE_STRING const *)

- ea: `0x14000bbb0`
- end: `0x14000bc7a`
- name: `?Create@PCW_NOTIFIER@@SAJPEAPEAXPEBU_UNICODE_STRING@@@Z`
- size: `202`
- prototype: `__int64 __fastcall(PHANDLE Handle, const struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000a1e0`

## callees

- `0x140008140`
- `0x14000b42c`
- `0x14000bbb0`
- `0x14000ca84`
- `0x14000d660`

## import_xrefs

- `ntoskrnl!ObInsertObject` at `0x14000bc4b`
- `ntoskrnl!ObInsertObject` at `0x14000bc4b`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x14000bbdc`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x14000bbdc`

## pseudocode

```c
NTSTATUS __fastcall PCW_NOTIFIER::Create(PHANDLE Handle, const struct _UNICODE_STRING *a2)
{
  NTSTATUS result; // eax
  __int64 v5; // rcx
  int inserted; // ebx
  __int64 v7; // r8
  __int64 v8; // r9
  void *v9; // rax
  void *v10; // [rsp+30h] [rbp-10h] BYREF
  __int64 v11; // [rsp+60h] [rbp+20h] BYREF
  _LUID Luid; // [rsp+68h] [rbp+28h] BYREF

  v11 = 0;
  Luid = 0;
  result = ZwAllocateLocallyUniqueId(&Luid);
  if ( result >= 0 )
  {
    inserted = PCW_COUNTERSET::FindOrCreate(&v11, a2, 1u);
    if ( inserted >= 0 )
    {
      v10 = 0;
      inserted = PcwpCreateObject(&v10, 40, v7, v8);
      if ( inserted >= 0 )
      {
        v9 = (void *)PCW_NOTIFIER::PCW_NOTIFIER(v10, &v11, &Luid);
        inserted = ObInsertObject(v9, 0, 2u, 0, 0, Handle);
      }
    }
    if ( v11 )
      ReleaseDeleter<PCW_COUNTERSET>::operator()(v5, v11);
    return inserted;
  }
  return result;
}

```

## disassembly

```asm
0x14000bbb0  mov     [rsp-8+arg_0], rbx
0x14000bbb5  mov     [rsp-8+arg_8], rdi
0x14000bbba  push    rbp
0x14000bbbb  mov     rbp, rsp
0x14000bbbe  sub     rsp, 40h
0x14000bbc2  mov     rdi, rcx
0x14000bbc5  mov     [rbp+arg_10], 0
0x14000bbcd  lea     rcx, [rbp+Luid]; Luid
0x14000bbd1  mov     qword ptr [rbp+Luid.LowPart], 0
0x14000bbd9  mov     rbx, rdx
0x14000bbdc  call    cs:__imp_ZwAllocateLocallyUniqueId
0x14000bbe3  nop     dword ptr [rax+rax+00h]
0x14000bbe8  test    eax, eax
0x14000bbea  js      short loc_14000BC69
0x14000bbec  mov     r8d, 1
0x14000bbf2  lea     rcx, [rbp+arg_10]
0x14000bbf6  mov     rdx, rbx
0x14000bbf9  call    ?FindOrCreate@PCW_COUNTERSET@@SAJPEAV?$unique_ptr@VPCW_COUNTERSET@@U?$ReleaseDeleter@VPCW_COUNTERSET@@@@@utl@@PEBU_UNICODE_STRING@@K@Z; PCW_COUNTERSET::FindOrCreate(utl::unique_ptr<PCW_COUNTERSET,ReleaseDeleter<PCW_COUNTERSET>> *,_UNICODE_STRING const *,ulong)
0x14000bbfe  mov     ebx, eax
0x14000bc00  test    eax, eax
0x14000bc02  js      short loc_14000BC59
0x14000bc04  mov     edx, 28h ; '('; unsigned int
0x14000bc09  mov     [rbp+var_10], 0
0x14000bc11  lea     rcx, [rbp+var_10]; void **
0x14000bc15  call    ?PcwpCreateObject@@YAJPEAPEAXK@Z; PcwpCreateObject(void * *,ulong)
0x14000bc1a  mov     ebx, eax
0x14000bc1c  test    eax, eax
0x14000bc1e  js      short loc_14000BC59
0x14000bc20  mov     rcx, [rbp+var_10]
0x14000bc24  lea     r8, [rbp+Luid]
0x14000bc28  lea     rdx, [rbp+arg_10]
0x14000bc2c  call    ??0PCW_NOTIFIER@@AEAA@$$QEAV?$unique_ptr@VPCW_COUNTERSET@@U?$ReleaseDeleter@VPCW_COUNTERSET@@@@@utl@@AEBU_LUID@@@Z; PCW_NOTIFIER::PCW_NOTIFIER(utl::unique_ptr<PCW_COUNTERSET,ReleaseDeleter<PCW_COUNTERSET>> &&,_LUID const &)
0x14000bc31  xor     r9d, r9d; ObjectPointerBias
0x14000bc34  mov     [rsp+40h+Handle], rdi; Handle
0x14000bc39  xor     edx, edx; PassedAccessState
0x14000bc3b  mov     [rsp+40h+NewObject], 0; NewObject
0x14000bc44  mov     rcx, rax; Object
0x14000bc47  lea     r8d, [r9+2]; DesiredAccess
0x14000bc4b  call    cs:__imp_ObInsertObject
0x14000bc52  nop     dword ptr [rax+rax+00h]
0x14000bc57  mov     ebx, eax
0x14000bc59  mov     rdx, [rbp+arg_10]
0x14000bc5d  test    rdx, rdx
0x14000bc60  jz      short loc_14000BC67
0x14000bc62  call    ??R?$ReleaseDeleter@VPCW_COUNTERSET@@@@QEBAXPEAVPCW_COUNTERSET@@@Z; ReleaseDeleter<PCW_COUNTERSET>::operator()(PCW_COUNTERSET *)
0x14000bc67  mov     eax, ebx
0x14000bc69  mov     rbx, [rsp+40h+arg_0]
0x14000bc6e  mov     rdi, [rsp+40h+arg_8]
0x14000bc73  add     rsp, 40h
0x14000bc77  pop     rbp
0x14000bc78  retn
```
