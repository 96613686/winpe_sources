# FTP_CONTROL_API_CLASS_FACTORY::Terminate(void)

- ea: `0x180017128`
- end: `0x1800171cb`
- name: `?Terminate@FTP_CONTROL_API_CLASS_FACTORY@@QEAAXXZ`
- size: `163`
- prototype: `void __fastcall(FTP_CONTROL_API_CLASS_FACTORY *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800047d0`
- `0x180004a18`

## callees

- `0x180017128`

## import_xrefs

- `KERNEL32!Sleep` at `0x1800171b3`
- `KERNEL32!Sleep` at `0x1800171b3`
- `ole32!CoRevokeClassObject` at `0x180017138`
- `ole32!CoRevokeClassObject` at `0x180017138`
- `ole32!CoDisconnectObject` at `0x180017187`
- `ole32!CoDisconnectObject` at `0x180017187`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180017195`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180017195`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800171a6`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800171a6`
- `iisutil!PuDbgPrintError` at `0x180017176`
- `iisutil!PuDbgPrintError` at `0x180017176`

## pseudocode

```c
void __fastcall FTP_CONTROL_API_CLASS_FACTORY::Terminate(FTP_CONTROL_API_CLASS_FACTORY *this)
{
  HRESULT v2; // eax
  IUnknown *v3; // rcx
  _DWORD *v4; // rdi

  v2 = CoRevokeClassObject(*((_DWORD *)this + 6));
  if ( v2 < 0 && (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_control_api_class_factory.cxx",
      120,
      "FTP_CONTROL_API_CLASS_FACTORY::Terminate",
      v2,
      "Revoking FTP_CONTROL_API_CLASS_FACTORY object failed.\n");
  v3 = (IUnknown *)*((_QWORD *)this + 2);
  if ( v3 )
  {
    CoDisconnectObject(v3, 0);
    v4 = (_DWORD *)*((_QWORD *)this + 2);
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(v4 + 4));
    v4[7] = 1;
    CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(v4 + 4));
    while ( v4[6] )
      Sleep(0xC8u);
  }
}

```

## disassembly

```asm
0x180017128  mov     [rsp+arg_0], rbx
0x18001712d  push    rdi
0x18001712e  sub     rsp, 30h
0x180017132  mov     rbx, rcx
0x180017135  mov     ecx, [rcx+18h]; dwRegister
0x180017138  call    cs:__imp_CoRevokeClassObject
0x18001713e  test    eax, eax
0x180017140  jns     short loc_18001717C
0x180017142  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180017149  jz      short loc_18001717C
0x18001714b  lea     rcx, aRevokingFtpCon; "Revoking FTP_CONTROL_API_CLASS_FACTORY "...
0x180017152  mov     r8d, 78h ; 'x'
0x180017158  mov     [rsp+38h+var_10], rcx
0x18001715d  lea     r9, aFtpControlApiC_0; "FTP_CONTROL_API_CLASS_FACTORY::Terminat"...
0x180017164  mov     rcx, cs:g_pDebug
0x18001716b  lea     rdx, aInetsrvIisIisr_31; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x180017172  mov     [rsp+38h+var_18], eax
0x180017176  call    cs:__imp_PuDbgPrintError
0x18001717c  mov     rcx, [rbx+10h]; pUnk
0x180017180  test    rcx, rcx
0x180017183  jz      short loc_1800171C0
0x180017185  xor     edx, edx; dwReserved
0x180017187  call    cs:__imp_CoDisconnectObject
0x18001718d  mov     rdi, [rbx+10h]
0x180017191  lea     rcx, [rdi+10h]
0x180017195  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18001719b  lea     rcx, [rdi+10h]
0x18001719f  mov     dword ptr [rdi+1Ch], 1
0x1800171a6  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800171ac  jmp     short loc_1800171B9
0x1800171ae  mov     ecx, 0C8h; dwMilliseconds
0x1800171b3  call    cs:__imp_Sleep
0x1800171b9  mov     eax, [rdi+18h]
0x1800171bc  test    eax, eax
0x1800171be  jnz     short loc_1800171AE
0x1800171c0  mov     rbx, [rsp+38h+arg_0]
0x1800171c5  add     rsp, 30h
0x1800171c9  pop     rdi
0x1800171ca  retn
```
