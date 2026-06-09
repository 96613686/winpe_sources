# CSystemWriter::AddCoreCbsFiles(IVssCreateWriterMetadata *,void *)

- ea: `0x18001e124`
- end: `0x18001e1cd`
- name: `?AddCoreCbsFiles@CSystemWriter@@AEAA_NPEAVIVssCreateWriterMetadata@@PEAX@Z`
- size: `169`
- prototype: `bool(CSystemWriter *__hidden this, struct IVssCreateWriterMetadata *, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001e1d4`

## callees

- `0x18001e308`

## string_xrefs

- `0x18001e156`: `%systemroot%\ServiceProfiles\LocalService\AppData\Roaming\Microsoft\Crypto`
- `0x18001e16a`: `%systemroot%\ServiceProfiles\NetworkService\AppData\Roaming\Microsoft\Crypto`
- `0x18001e17f`: `%systemroot%\System32\Microsoft\Crypto`
- `0x18001e193`: `%ProgramData%\Microsoft\Crypto`
- `0x18001e1a8`: `%systemroot%\System32\Microsoft\Protect`

## pseudocode

```c
bool __fastcall CSystemWriter::AddCoreCbsFiles(CSystemWriter *this, struct IVssCreateWriterMetadata *a2, void *a3)
{
  bool v4; // bl
  CSystemWriter *v5; // rcx
  char v6; // di
  CSystemWriter *v7; // rcx
  char v8; // bl
  CSystemWriter *v9; // rcx
  char v10; // di
  CSystemWriter *v11; // rcx
  char v12; // bl
  CSystemWriter *v13; // rcx
  char v14; // di
  CSystemWriter *v15; // rcx

  v4 = CSystemWriter::AddPathToWriterMetadata(this, a2, L"%systemroot%\\servicing\\packages");
  v6 = v4 & CSystemWriter::AddPathToWriterMetadata(v5, a2, L"%systemroot%\\servicing\\Version");
  v8 = v6
     & CSystemWriter::AddPathToWriterMetadata(
         v7,
         a2,
         L"%systemroot%\\ServiceProfiles\\LocalService\\AppData\\Roaming\\Microsoft\\Crypto");
  v10 = v8
      & CSystemWriter::AddPathToWriterMetadata(
          v9,
          a2,
          L"%systemroot%\\ServiceProfiles\\NetworkService\\AppData\\Roaming\\Microsoft\\Crypto");
  v12 = v10 & CSystemWriter::AddPathToWriterMetadata(v11, a2, L"%systemroot%\\System32\\Microsoft\\Crypto");
  v14 = v12 & CSystemWriter::AddPathToWriterMetadata(v13, a2, L"%ProgramData%\\Microsoft\\Crypto");
  return v14 & CSystemWriter::AddPathToWriterMetadata(v15, a2, L"%systemroot%\\System32\\Microsoft\\Protect");
}

```

## disassembly

```asm
0x18001e124  mov     [rsp+arg_0], rbx
0x18001e129  mov     [rsp+arg_8], rsi
0x18001e12e  push    rdi
0x18001e12f  sub     rsp, 20h
0x18001e133  lea     r8, aSystemrootServ_0; "%systemroot%\\servicing\\packages"
0x18001e13a  mov     rsi, rdx
0x18001e13d  call    ?AddPathToWriterMetadata@CSystemWriter@@AEAA_NPEAVIVssCreateWriterMetadata@@PEAG@Z; CSystemWriter::AddPathToWriterMetadata(IVssCreateWriterMetadata *,ushort *)
0x18001e142  lea     r8, aSystemrootServ_3; "%systemroot%\\servicing\\Version"
0x18001e149  mov     rdx, rsi; struct IVssCreateWriterMetadata *
0x18001e14c  mov     bl, al
0x18001e14e  call    ?AddPathToWriterMetadata@CSystemWriter@@AEAA_NPEAVIVssCreateWriterMetadata@@PEAG@Z; CSystemWriter::AddPathToWriterMetadata(IVssCreateWriterMetadata *,ushort *)
0x18001e153  mov     dil, al
0x18001e156  lea     r8, aSystemrootServ_2; "%systemroot%\\ServiceProfiles\\LocalSer"...
0x18001e15d  mov     rdx, rsi; struct IVssCreateWriterMetadata *
0x18001e160  and     dil, bl
0x18001e163  call    ?AddPathToWriterMetadata@CSystemWriter@@AEAA_NPEAVIVssCreateWriterMetadata@@PEAG@Z; CSystemWriter::AddPathToWriterMetadata(IVssCreateWriterMetadata *,ushort *)
0x18001e168  mov     bl, al
0x18001e16a  lea     r8, aSystemrootServ_1; "%systemroot%\\ServiceProfiles\\NetworkS"...
0x18001e171  mov     rdx, rsi; struct IVssCreateWriterMetadata *
0x18001e174  and     bl, dil
0x18001e177  call    ?AddPathToWriterMetadata@CSystemWriter@@AEAA_NPEAVIVssCreateWriterMetadata@@PEAG@Z; CSystemWriter::AddPathToWriterMetadata(IVssCreateWriterMetadata *,ushort *)
0x18001e17c  mov     dil, al
0x18001e17f  lea     r8, aSystemrootSyst; "%systemroot%\\System32\\Microsoft\\Cryp"...
0x18001e186  mov     rdx, rsi; struct IVssCreateWriterMetadata *
0x18001e189  and     dil, bl
0x18001e18c  call    ?AddPathToWriterMetadata@CSystemWriter@@AEAA_NPEAVIVssCreateWriterMetadata@@PEAG@Z; CSystemWriter::AddPathToWriterMetadata(IVssCreateWriterMetadata *,ushort *)
0x18001e191  mov     bl, al
0x18001e193  lea     r8, aProgramdataMic; "%ProgramData%\\Microsoft\\Crypto"
0x18001e19a  mov     rdx, rsi; struct IVssCreateWriterMetadata *
0x18001e19d  and     bl, dil
0x18001e1a0  call    ?AddPathToWriterMetadata@CSystemWriter@@AEAA_NPEAVIVssCreateWriterMetadata@@PEAG@Z; CSystemWriter::AddPathToWriterMetadata(IVssCreateWriterMetadata *,ushort *)
0x18001e1a5  mov     dil, al
0x18001e1a8  lea     r8, aSystemrootSyst_0; "%systemroot%\\System32\\Microsoft\\Prot"...
0x18001e1af  mov     rdx, rsi; struct IVssCreateWriterMetadata *
0x18001e1b2  and     dil, bl
0x18001e1b5  call    ?AddPathToWriterMetadata@CSystemWriter@@AEAA_NPEAVIVssCreateWriterMetadata@@PEAG@Z; CSystemWriter::AddPathToWriterMetadata(IVssCreateWriterMetadata *,ushort *)
0x18001e1ba  mov     rbx, [rsp+28h+arg_0]
0x18001e1bf  and     al, dil
0x18001e1c2  mov     rsi, [rsp+28h+arg_8]
0x18001e1c7  add     rsp, 20h
0x18001e1cb  pop     rdi
0x18001e1cc  retn
```
