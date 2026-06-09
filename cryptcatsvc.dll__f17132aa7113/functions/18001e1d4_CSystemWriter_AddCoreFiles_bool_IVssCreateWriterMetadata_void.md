# CSystemWriter::AddCoreFiles(bool,IVssCreateWriterMetadata *,void *)

- ea: `0x18001e1d4`
- end: `0x18001e2ff`
- name: `?AddCoreFiles@CSystemWriter@@AEAA_N_NPEAVIVssCreateWriterMetadata@@PEAX@Z`
- size: `299`
- prototype: `bool(CSystemWriter *__hidden this, bool, struct IVssCreateWriterMetadata *, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001e890`

## callees

- `0x180004d30`
- `0x1800056f0`
- `0x180006e54`
- `0x180007320`
- `0x1800076b0`
- `0x18000be40`
- `0x18001df9c`
- `0x18001e124`
- `0x18001e1d4`
- `0x18001e308`
- `0x180020708`

## string_xrefs

- `0x18001e2d3`: `SystemShutdown initiated during stFileCallback`
- `0x18001e22e`: `%systemroot%\ServiceProfiles\NetworkService\AppData\Roaming\Microsoft\SoftwareProtectionPlatform`

## pseudocode

```c
char __fastcall CSystemWriter::AddCoreFiles(
        CSystemWriter *this,
        char a2,
        struct IVssCreateWriterMetadata *a3,
        void *a4)
{
  CSystemWriter *v8; // rcx
  char v9; // bl
  void *v10; // r8
  CSystemWriter *v11; // rcx
  CSystemWriter *v12; // rcx
  struct IVssCreateWriterMetadata *v13; // rdx
  CSystemWriter *v14; // rcx
  CSystemWriter *v15; // rcx
  __int64 v17[2]; // [rsp+30h] [rbp-58h] BYREF
  __int128 v18; // [rsp+40h] [rbp-48h]

  *(_OWORD *)v17 = 0;
  v18 = 0;
  v9 = CSystemWriter::AddCoreCsiFiles(this, a3, a4);
  if ( v9 )
  {
    v9 = CSystemWriter::AddCoreCbsFiles(v8, a3, v10);
    if ( v9 )
    {
      if ( !CSystemWriter::AddPathToWriterMetadata(
              v11,
              a3,
              L"%systemroot%\\ServiceProfiles\\NetworkService\\AppData\\Roaming\\Microsoft\\SoftwareProtectionPlatform") )
        return 0;
      v9 = CSystemWriter::AddCorePnPFiles(v12, a3, a4);
      if ( v9 )
      {
        v9 = CSystemWriter::AddLegacyDriverFiles(v14, v13, a4);
        if ( v9 )
        {
          if ( !a2 || (v9 = CSystemWriter::AddWin32ServiceFiles(v15, 0, a4)) != 0 )
          {
            v9 = CSystemWriter::AddCoreCLRFiles(v15, a3, a4);
            if ( v9 )
            {
              v17[0] = (__int64)a3;
              *(_QWORD *)&v18 = L"System Files";
              LODWORD(v17[1]) = 0;
              *((_QWORD *)&v18 + 1) = this;
              pSetupStringTableEnum(a4, (__int64)v17);
              if ( SLODWORD(v17[1]) < 0 )
              {
                if ( LODWORD(v17[1]) == -1073741077 )
                  CSystemWriter::LogSystemErrorEvent(0x201u, L"SystemShutdown initiated during stFileCallback", 0x281u);
                return 0;
              }
            }
          }
        }
      }
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18001e1d4  push    rbx
0x18001e1d6  push    rbp
0x18001e1d7  push    rsi
0x18001e1d8  push    rdi
0x18001e1d9  push    r14
0x18001e1db  sub     rsp, 60h
0x18001e1df  mov     rax, cs:__security_cookie
0x18001e1e6  xor     rax, rsp
0x18001e1e9  mov     [rsp+88h+var_38], rax
0x18001e1ee  mov     rsi, r8
0x18001e1f1  xorps   xmm0, xmm0
0x18001e1f4  mov     bpl, dl
0x18001e1f7  mov     r8, r9; void *
0x18001e1fa  mov     rdx, rsi; struct IVssCreateWriterMetadata *
0x18001e1fd  mov     rdi, r9
0x18001e200  mov     r14, rcx
0x18001e203  movups  xmmword ptr [rsp+88h+var_58], xmm0
0x18001e208  movups  [rsp+88h+var_48], xmm0
0x18001e20d  call    ?AddCoreCsiFiles@CSystemWriter@@AEAA_NPEAVIVssCreateWriterMetadata@@PEAX@Z; CSystemWriter::AddCoreCsiFiles(IVssCreateWriterMetadata *,void *)
0x18001e212  mov     bl, al
0x18001e214  test    al, al
0x18001e216  jz      loc_18001E2E5
0x18001e21c  mov     rdx, rsi; struct IVssCreateWriterMetadata *
0x18001e21f  call    ?AddCoreCbsFiles@CSystemWriter@@AEAA_NPEAVIVssCreateWriterMetadata@@PEAX@Z; CSystemWriter::AddCoreCbsFiles(IVssCreateWriterMetadata *,void *)
0x18001e224  mov     bl, al
0x18001e226  test    al, al
0x18001e228  jz      loc_18001E2E5
0x18001e22e  lea     r8, aSystemrootServ; "%systemroot%\\ServiceProfiles\\NetworkS"...
0x18001e235  mov     rdx, rsi; struct IVssCreateWriterMetadata *
0x18001e238  call    ?AddPathToWriterMetadata@CSystemWriter@@AEAA_NPEAVIVssCreateWriterMetadata@@PEAG@Z; CSystemWriter::AddPathToWriterMetadata(IVssCreateWriterMetadata *,ushort *)
0x18001e23d  test    al, al
0x18001e23f  jz      loc_18001E2E3
0x18001e245  mov     r8, rdi; void *
0x18001e248  mov     rdx, rsi; struct IVssCreateWriterMetadata *
0x18001e24b  call    ?AddCorePnPFiles@CSystemWriter@@AEAA_NPEAVIVssCreateWriterMetadata@@PEAX@Z; CSystemWriter::AddCorePnPFiles(IVssCreateWriterMetadata *,void *)
0x18001e250  mov     bl, al
0x18001e252  test    al, al
0x18001e254  jz      loc_18001E2E5
0x18001e25a  mov     r8, rdi; void *
0x18001e25d  call    ?AddLegacyDriverFiles@CSystemWriter@@AEAA_NPEAVIVssCreateWriterMetadata@@PEAX@Z; CSystemWriter::AddLegacyDriverFiles(IVssCreateWriterMetadata *,void *)
0x18001e262  mov     bl, al
0x18001e264  test    al, al
0x18001e266  jz      short loc_18001E2E5
0x18001e268  test    bpl, bpl
0x18001e26b  jz      short loc_18001E27D
0x18001e26d  mov     r8, rdi; void *
0x18001e270  xor     edx, edx; void *
0x18001e272  call    ?AddWin32ServiceFiles@CSystemWriter@@AEAA_NPEAX0@Z; CSystemWriter::AddWin32ServiceFiles(void *,void *)
0x18001e277  mov     bl, al
0x18001e279  test    al, al
0x18001e27b  jz      short loc_18001E2E5
0x18001e27d  mov     r8, rdi; void *
0x18001e280  mov     rdx, rsi; struct IVssCreateWriterMetadata *
0x18001e283  call    ?AddCoreCLRFiles@CSystemWriter@@AEAA_NPEAVIVssCreateWriterMetadata@@PEAX@Z; CSystemWriter::AddCoreCLRFiles(IVssCreateWriterMetadata *,void *)
0x18001e288  mov     bl, al
0x18001e28a  test    al, al
0x18001e28c  jz      short loc_18001E2E5
0x18001e28e  lea     rax, aSystemFiles; "System Files"
0x18001e295  mov     [rsp+88h+var_58], rsi
0x18001e29a  mov     qword ptr [rsp+88h+var_48], rax
0x18001e29f  mov     rcx, rdi; void *
0x18001e2a2  lea     rax, [rsp+88h+var_58]
0x18001e2a7  mov     dword ptr [rsp+88h+var_58+8], 0
0x18001e2af  mov     [rsp+88h+var_68], rax; __int64
0x18001e2b4  mov     qword ptr [rsp+88h+var_48+8], r14
0x18001e2b9  call    pSetupStringTableEnum
0x18001e2be  mov     eax, dword ptr [rsp+88h+var_58+8]
0x18001e2c2  test    eax, eax
0x18001e2c4  jns     short loc_18001E2E5
0x18001e2c6  cmp     eax, 0C00002EBh
0x18001e2cb  jnz     short loc_18001E2E3
0x18001e2cd  mov     r8d, 281h; unsigned int
0x18001e2d3  lea     rdx, aSystemshutdown; "SystemShutdown initiated during stFileC"...
0x18001e2da  lea     ecx, [r8-80h]; unsigned int
0x18001e2de  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x18001e2e3  xor     bl, bl
0x18001e2e5  mov     al, bl
0x18001e2e7  mov     rcx, [rsp+88h+var_38]
0x18001e2ec  xor     rcx, rsp; StackCookie
0x18001e2ef  call    __security_check_cookie
0x18001e2f4  add     rsp, 60h
0x18001e2f8  pop     r14
0x18001e2fa  pop     rdi
0x18001e2fb  pop     rsi
0x18001e2fc  pop     rbp
0x18001e2fd  pop     rbx
0x18001e2fe  retn
```
