# CSystemWriter::OnIdentify(IVssCreateWriterMetadata *)

- ea: `0x18001e890`
- end: `0x18001ea49`
- name: `?OnIdentify@CSystemWriter@@UEAA_NPEAVIVssCreateWriterMetadata@@@Z`
- size: `441`
- prototype: `bool __fastcall(CSystemWriter *__hidden this, struct IVssCreateWriterMetadata *)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180004824`
- `0x180006e54`
- `0x18001e1d4`
- `0x18001e39c`
- `0x18001e71c`
- `0x18001e890`
- `0x18001ff98`
- `0x180020050`
- `0x1800206c8`
- `0x18002078c`
- `0x180022010`

## string_xrefs

- `0x18001e9b8`: `Win32 Services Files`
- `0x18001e963`: `OnIdentity() : AddComponent() call failed for System Files component.`
- `0x18001ea08`: `OnIdentity() : AddComponent() call failed for Win32 Services Files component.`

## pseudocode

```c
char __fastcall CSystemWriter::OnIdentify(CSystemWriter *this, struct IVssCreateWriterMetadata *a2)
{
  void *v4; // rbx
  char v5; // si
  signed int v6; // eax
  CSystemWriter *v7; // rcx
  const unsigned __int16 *v8; // rdx
  BOOL IsWin32ServicesComponentRequired; // r14d
  char v11; // [rsp+28h] [rbp-70h]

  v4 = 0;
  if ( (unsigned int)pSetupInitializeUtils() )
  {
    v4 = (void *)pSetupStringTableInitialize();
    if ( v4 )
    {
      v5 = 1;
      v11 = 1;
      v6 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, __int64, _QWORD, _QWORD, int, char))(*(_QWORD *)a2 + 48LL))(
             a2,
             6,
             0,
             0,
             1,
             v11);
      if ( v6 )
      {
        v8 = L"OnIdentity() : SetRestoreMethod() call failed.";
LABEL_5:
        CSystemWriter::LogSystemErrorEvent(0x201u, v8, v6);
        goto LABEL_15;
      }
      IsWin32ServicesComponentRequired = CSystemWriter::IsWin32ServicesComponentRequired(v7);
      v6 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, __int64))(*(_QWORD *)a2 + 16LL))(a2, 2);
      if ( v6 )
      {
        v8 = L"OnIdentity() : AddComponent() call failed for System Files component.";
        goto LABEL_5;
      }
      if ( CSystemWriter::AddCatalogFiles(this, a2, 0)
        && CSystemWriter::AddCatalogFiles(this, a2, 1)
        && CSystemWriter::AddCoreFiles(this, !IsWin32ServicesComponentRequired, a2, v4) )
      {
        if ( !IsWin32ServicesComponentRequired )
          goto LABEL_16;
        v6 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, __int64))(*(_QWORD *)a2 + 16LL))(a2, 2);
        if ( v6 < 0 )
        {
          v8 = L"OnIdentity() : AddComponent() call failed for Win32 Services Files component.";
          goto LABEL_5;
        }
        if ( CSystemWriter::AddWin32ServiceFilesComponent(this, a2, v4) )
        {
LABEL_16:
          pSetupStringTableDestroy(v4);
          goto LABEL_17;
        }
      }
    }
  }
LABEL_15:
  v5 = 0;
  if ( v4 )
    goto LABEL_16;
LABEL_17:
  pSetupUninitializeUtils();
  return v5;
}

```

## disassembly

```asm
0x18001e890  push    rbx
0x18001e892  push    rbp
0x18001e893  push    rsi
0x18001e894  push    rdi
0x18001e895  push    r14
0x18001e897  sub     rsp, 70h
0x18001e89b  mov     rdi, rdx
0x18001e89e  mov     rbp, rcx
0x18001e8a1  xor     ebx, ebx
0x18001e8a3  call    pSetupInitializeUtils
0x18001e8a8  test    eax, eax
0x18001e8aa  jz      loc_18001EA26
0x18001e8b0  call    pSetupStringTableInitialize
0x18001e8b5  mov     rbx, rax
0x18001e8b8  test    rax, rax
0x18001e8bb  jz      loc_18001EA26
0x18001e8c1  mov     rdx, [rdi]
0x18001e8c4  mov     esi, 1
0x18001e8c9  mov     byte ptr [rsp+98h+var_70], sil
0x18001e8ce  xor     r9d, r9d
0x18001e8d1  xor     r8d, r8d
0x18001e8d4  mov     dword ptr [rsp+98h+var_78], esi
0x18001e8d8  mov     rcx, rdi
0x18001e8db  mov     rax, [rdx+30h]
0x18001e8df  lea     edx, [rsi+5]
0x18001e8e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8e7  test    eax, eax
0x18001e8e9  jz      short loc_18001E904
0x18001e8eb  lea     rdx, aOnidentitySetr; "OnIdentity() : SetRestoreMethod() call "...
0x18001e8f2  mov     r8d, eax; unsigned int
0x18001e8f5  mov     ecx, 201h; unsigned int
0x18001e8fa  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x18001e8ff  jmp     loc_18001EA26
0x18001e904  call    ?IsWin32ServicesComponentRequired@CSystemWriter@@AEAAHXZ; CSystemWriter::IsWin32ServicesComponentRequired(void)
0x18001e909  mov     rcx, [rdi]
0x18001e90c  lea     r9, aSystemFiles; "System Files"
0x18001e913  mov     [rsp+98h+var_40], 0
0x18001e91b  test    eax, eax
0x18001e91d  mov     [rsp+98h+var_48], 0
0x18001e922  mov     r14d, eax
0x18001e925  setnz   dl
0x18001e928  xor     r8d, r8d
0x18001e92b  mov     rax, [rcx+10h]
0x18001e92f  mov     rcx, rdi
0x18001e932  mov     [rsp+98h+var_50], dl
0x18001e936  mov     [rsp+98h+var_58], 0
0x18001e93b  mov     [rsp+98h+var_60], 0
0x18001e940  lea     edx, [r8+2]
0x18001e944  mov     [rsp+98h+var_68], 0
0x18001e94c  mov     [rsp+98h+var_70], 0
0x18001e955  mov     [rsp+98h+var_78], r9
0x18001e95a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e95f  test    eax, eax
0x18001e961  jz      short loc_18001E96C
0x18001e963  lea     rdx, aOnidentityAddc_0; "OnIdentity() : AddComponent() call fail"...
0x18001e96a  jmp     short loc_18001E8F2
0x18001e96c  xor     r8d, r8d; bool
0x18001e96f  mov     rdx, rdi; struct IVssCreateWriterMetadata *
0x18001e972  mov     rcx, rbp; this
0x18001e975  call    ?AddCatalogFiles@CSystemWriter@@AEAA_NPEAVIVssCreateWriterMetadata@@_N@Z; CSystemWriter::AddCatalogFiles(IVssCreateWriterMetadata *,bool)
0x18001e97a  test    al, al
0x18001e97c  jz      loc_18001EA26
0x18001e982  mov     r8b, sil; bool
0x18001e985  mov     rdx, rdi; struct IVssCreateWriterMetadata *
0x18001e988  mov     rcx, rbp; this
0x18001e98b  call    ?AddCatalogFiles@CSystemWriter@@AEAA_NPEAVIVssCreateWriterMetadata@@_N@Z; CSystemWriter::AddCatalogFiles(IVssCreateWriterMetadata *,bool)
0x18001e990  test    al, al
0x18001e992  jz      loc_18001EA26
0x18001e998  test    r14d, r14d
0x18001e99b  mov     r9, rbx; void *
0x18001e99e  mov     r8, rdi; struct IVssCreateWriterMetadata *
0x18001e9a1  mov     rcx, rbp; this
0x18001e9a4  setz    dl; bool
0x18001e9a7  call    ?AddCoreFiles@CSystemWriter@@AEAA_N_NPEAVIVssCreateWriterMetadata@@PEAX@Z; CSystemWriter::AddCoreFiles(bool,IVssCreateWriterMetadata *,void *)
0x18001e9ac  test    al, al
0x18001e9ae  jz      short loc_18001EA26
0x18001e9b0  test    r14d, r14d
0x18001e9b3  jz      short loc_18001EA2E
0x18001e9b5  mov     rax, [rdi]
0x18001e9b8  lea     r9, aWin32ServicesF; "Win32 Services Files"
0x18001e9bf  mov     [rsp+98h+var_40], 4
0x18001e9c7  xor     r8d, r8d
0x18001e9ca  mov     [rsp+98h+var_48], 0
0x18001e9cf  mov     rcx, rdi
0x18001e9d2  mov     [rsp+98h+var_50], sil
0x18001e9d7  mov     rax, [rax+10h]
0x18001e9db  mov     [rsp+98h+var_58], 0
0x18001e9e0  lea     edx, [r8+2]
0x18001e9e4  mov     [rsp+98h+var_60], 0
0x18001e9e9  mov     [rsp+98h+var_68], 0
0x18001e9f1  mov     [rsp+98h+var_70], 0
0x18001e9fa  mov     [rsp+98h+var_78], r9
0x18001e9ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea04  test    eax, eax
0x18001ea06  jns     short loc_18001EA14
0x18001ea08  lea     rdx, aOnidentityAddc; "OnIdentity() : AddComponent() call fail"...
0x18001ea0f  jmp     loc_18001E8F2
0x18001ea14  mov     r8, rbx; void *
0x18001ea17  mov     rdx, rdi; struct IVssCreateWriterMetadata *
0x18001ea1a  mov     rcx, rbp; this
0x18001ea1d  call    ?AddWin32ServiceFilesComponent@CSystemWriter@@AEAA_NPEAVIVssCreateWriterMetadata@@PEAX@Z; CSystemWriter::AddWin32ServiceFilesComponent(IVssCreateWriterMetadata *,void *)
0x18001ea22  test    al, al
0x18001ea24  jnz     short loc_18001EA2E
0x18001ea26  xor     sil, sil
0x18001ea29  test    rbx, rbx
0x18001ea2c  jz      short loc_18001EA36
0x18001ea2e  mov     rcx, rbx
0x18001ea31  call    pSetupStringTableDestroy
0x18001ea36  call    pSetupUninitializeUtils
0x18001ea3b  mov     al, sil
0x18001ea3e  add     rsp, 70h
0x18001ea42  pop     r14
0x18001ea44  pop     rdi
0x18001ea45  pop     rsi
0x18001ea46  pop     rbp
0x18001ea47  pop     rbx
0x18001ea48  retn
```
