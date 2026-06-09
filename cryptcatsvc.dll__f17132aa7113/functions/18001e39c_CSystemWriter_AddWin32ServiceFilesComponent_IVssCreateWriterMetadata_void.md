# CSystemWriter::AddWin32ServiceFilesComponent(IVssCreateWriterMetadata *,void *)

- ea: `0x18001e39c`
- end: `0x18001e467`
- name: `?AddWin32ServiceFilesComponent@CSystemWriter@@AEAA_NPEAVIVssCreateWriterMetadata@@PEAX@Z`
- size: `203`
- prototype: `bool(CSystemWriter *__hidden this, struct IVssCreateWriterMetadata *, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001e890`

## callees

- `0x180004d30`
- `0x180006e54`
- `0x18000be40`
- `0x18001e39c`
- `0x1800206c8`
- `0x180020708`
- `0x18002078c`

## string_xrefs

- `0x18001e3ec`: `Win32 Services Files`
- `0x18001e431`: `SystemShutdown initiated during stFileCallback`

## pseudocode

```c
bool __fastcall CSystemWriter::AddWin32ServiceFilesComponent(
        CSystemWriter *this,
        struct IVssCreateWriterMetadata *a2,
        void *a3)
{
  void *v6; // rax
  CSystemWriter *v7; // rcx
  void *v8; // rdi
  bool v9; // bl
  __int64 v11[2]; // [rsp+30h] [rbp-58h] BYREF
  __int128 v12; // [rsp+40h] [rbp-48h]

  *(_OWORD *)v11 = 0;
  v12 = 0;
  v6 = (void *)pSetupStringTableInitialize();
  v8 = v6;
  if ( !v6 )
    return 0;
  v9 = CSystemWriter::AddWin32ServiceFiles(v7, a3, v6);
  if ( v9 )
  {
    v11[0] = (__int64)a2;
    *(_QWORD *)&v12 = L"Win32 Services Files";
    LODWORD(v11[1]) = 0;
    *((_QWORD *)&v12 + 1) = this;
    pSetupStringTableEnum(v8, (__int64)v11);
    if ( SLODWORD(v11[1]) >= 0 )
    {
      v9 = 1;
    }
    else
    {
      if ( LODWORD(v11[1]) == -1073741077 )
        CSystemWriter::LogSystemErrorEvent(0x201u, L"SystemShutdown initiated during stFileCallback", 0x281u);
      v9 = 0;
    }
  }
  pSetupStringTableDestroy(v8);
  return v9;
}

```

## disassembly

```asm
0x18001e39c  push    rbx
0x18001e39e  push    rbp
0x18001e39f  push    rsi
0x18001e3a0  push    rdi
0x18001e3a1  sub     rsp, 68h
0x18001e3a5  mov     rax, cs:__security_cookie
0x18001e3ac  xor     rax, rsp
0x18001e3af  mov     [rsp+88h+var_38], rax
0x18001e3b4  xorps   xmm0, xmm0
0x18001e3b7  mov     rbx, r8
0x18001e3ba  movups  xmmword ptr [rsp+88h+var_58], xmm0
0x18001e3bf  mov     rsi, rdx
0x18001e3c2  mov     rbp, rcx
0x18001e3c5  movups  [rsp+88h+var_48], xmm0
0x18001e3ca  call    pSetupStringTableInitialize
0x18001e3cf  mov     rdi, rax
0x18001e3d2  test    rax, rax
0x18001e3d5  jnz     short loc_18001E3DB
0x18001e3d7  xor     bl, bl
0x18001e3d9  jmp     short loc_18001E44F
0x18001e3db  mov     r8, rdi; void *
0x18001e3de  mov     rdx, rbx; void *
0x18001e3e1  call    ?AddWin32ServiceFiles@CSystemWriter@@AEAA_NPEAX0@Z; CSystemWriter::AddWin32ServiceFiles(void *,void *)
0x18001e3e6  mov     bl, al
0x18001e3e8  test    al, al
0x18001e3ea  jz      short loc_18001E447
0x18001e3ec  lea     rax, aWin32ServicesF; "Win32 Services Files"
0x18001e3f3  mov     [rsp+88h+var_58], rsi
0x18001e3f8  mov     qword ptr [rsp+88h+var_48], rax
0x18001e3fd  mov     rcx, rdi; void *
0x18001e400  lea     rax, [rsp+88h+var_58]
0x18001e405  mov     dword ptr [rsp+88h+var_58+8], 0
0x18001e40d  mov     [rsp+88h+var_68], rax; __int64
0x18001e412  mov     qword ptr [rsp+88h+var_48+8], rbp
0x18001e417  call    pSetupStringTableEnum
0x18001e41c  mov     eax, dword ptr [rsp+88h+var_58+8]
0x18001e420  test    eax, eax
0x18001e422  jns     short loc_18001E445
0x18001e424  cmp     eax, 0C00002EBh
0x18001e429  jnz     short loc_18001E441
0x18001e42b  mov     r8d, 281h; unsigned int
0x18001e431  lea     rdx, aSystemshutdown; "SystemShutdown initiated during stFileC"...
0x18001e438  lea     ecx, [r8-80h]; unsigned int
0x18001e43c  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x18001e441  xor     bl, bl
0x18001e443  jmp     short loc_18001E447
0x18001e445  mov     bl, 1
0x18001e447  mov     rcx, rdi
0x18001e44a  call    pSetupStringTableDestroy
0x18001e44f  mov     al, bl
0x18001e451  mov     rcx, [rsp+88h+var_38]
0x18001e456  xor     rcx, rsp; StackCookie
0x18001e459  call    __security_check_cookie
0x18001e45e  add     rsp, 68h
0x18001e462  pop     rdi
0x18001e463  pop     rsi
0x18001e464  pop     rbp
0x18001e465  pop     rbx
0x18001e466  retn
```
