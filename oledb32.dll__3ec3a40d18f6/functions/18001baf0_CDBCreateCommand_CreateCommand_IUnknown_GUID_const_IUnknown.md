# CDBCreateCommand::CreateCommand(IUnknown *,_GUID const &,IUnknown * *)

- ea: `0x18001baf0`
- end: `0x18001c2aa`
- name: `?CreateCommand@CDBCreateCommand@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAU2@@Z`
- size: `1978`
- prototype: `__int64 __fastcall(CDBCreateCommand *__hidden this, struct IUnknown *, const struct _GUID *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x180013870`
- `0x18001baf0`
- `0x18001ceb0`
- `0x180029560`
- `0x18002a914`
- `0x18002a93c`
- `0x18002b644`
- `0x18002c060`
- `0x18002ec0c`
- `0x18006e3b0`
- `0x180087010`

## string_xrefs

- `0x18001bb43`: `<CDBCreateCommand::CreateCommand|OLEDB|ERR> `
- `0x18001bb92`: `<CDBCreateCommand::CreateCommand|OLEDB|ERR> `
- `0x18001bbd2`: `<CDBCreateCommand::CreateCommand|OLEDB|ERR> `
- `0x18001bbf0`: `<CDBCreateCommand::CreateCommand|OLEDB|ERR> `
- `0x18001bc71`: `<CDBCreateCommand::CreateCommand|OLEDB|ERR> `
- `0x18001bc8f`: `<CDBCreateCommand::CreateCommand|OLEDB|ERR> `
- `0x18001bd02`: `<CDBCreateCommand::CreateCommand|OLEDB|ERR> `
- `0x18001bd20`: `<CDBCreateCommand::CreateCommand|OLEDB|ERR> `
- `0x18001bd8a`: `<CDBCreateCommand::CreateCommand|OLEDB|ERR> `
- `0x18001bdf5`: `<CDBCreateCommand::CreateCommand|OLEDB|ERR> `
- `0x18001be6e`: `<CDBCreateCommand::CreateCommand|OLEDB|ERR> `
- `0x18001be8c`: `<CDBCreateCommand::CreateCommand|OLEDB|ERR> `
- `0x18001bf10`: `<CDBCreateCommand::CreateCommand|OLEDB|ERR> `
- `0x18001bf2e`: `<CDBCreateCommand::CreateCommand|OLEDB|ERR> `
- `0x18001bf99`: `<CDBCreateCommand::CreateCommand|OLEDB|ERR> `
- `0x18001c057`: `<CDBCreateCommand::CreateCommand|OLEDB|ERR> `
- `0x18001c075`: `<CDBCreateCommand::CreateCommand|OLEDB|ERR> `
- `0x18001c1f4`: `<CDBCreateCommand::CreateCommand|OLEDB|ERR> `
- `0x18001c212`: `<CDBCreateCommand::CreateCommand|OLEDB|ERR> `
- `0x18001bc0b`: `<CDBCreateCommand::CreateCommand|Trace|HR> `
- `0x18001bcaa`: `<CDBCreateCommand::CreateCommand|Trace|HR> `
- `0x18001bd3b`: `<CDBCreateCommand::CreateCommand|Trace|HR> `
- `0x18001bda5`: `<CDBCreateCommand::CreateCommand|Trace|HR> `
- `0x18001be10`: `<CDBCreateCommand::CreateCommand|Trace|HR> `
- `0x18001bea7`: `<CDBCreateCommand::CreateCommand|Trace|HR> `
- `0x18001bf49`: `<CDBCreateCommand::CreateCommand|Trace|HR> `
- `0x18001bfb4`: `<CDBCreateCommand::CreateCommand|Trace|HR> `
- `0x18001c090`: `<CDBCreateCommand::CreateCommand|Trace|HR> `
- `0x18001c22d`: `<CDBCreateCommand::CreateCommand|Trace|HR> `
- `0x18001c270`: `<CDBCreateCommand::CreateCommand|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CDBCreateCommand::CreateCommand(
        void **this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        struct IUnknown **a4)
{
  __int64 v8; // rax
  int v9; // edi
  struct IUnknown *v10; // rsi
  int v11; // edi
  CAcm *v12; // r15
  int v13; // edi
  _QWORD *v14; // rax
  int v15; // edi
  __int64 (__fastcall ***v16)(_QWORD, GUID *, __int64 *); // rcx
  int v17; // edi
  int v18; // edi
  int v19; // edi
  __int64 v20; // rbx
  int v21; // edi
  __int64 v22; // rcx
  int v23; // edi
  CDCM *RootAcm; // rax
  CDPO *CDPO; // rax
  int v26; // ebx
  int v27; // [rsp+30h] [rbp-98h]
  CAcm *v28; // [rsp+38h] [rbp-90h] BYREF
  __int64 v29; // [rsp+40h] [rbp-88h] BYREF
  __int64 v30; // [rsp+48h] [rbp-80h] BYREF
  struct IUnknown *v31; // [rsp+50h] [rbp-78h] BYREF
  int pExceptionObject; // [rsp+58h] [rbp-70h] BYREF
  int v33; // [rsp+5Ch] [rbp-6Ch] BYREF
  int v34; // [rsp+60h] [rbp-68h] BYREF
  int v35; // [rsp+64h] [rbp-64h] BYREF
  int v36; // [rsp+68h] [rbp-60h] BYREF
  int v37; // [rsp+6Ch] [rbp-5Ch] BYREF
  int v38; // [rsp+70h] [rbp-58h] BYREF
  int v39; // [rsp+74h] [rbp-54h] BYREF
  int v40; // [rsp+78h] [rbp-50h] BYREF
  int v41; // [rsp+7Ch] [rbp-4Ch] BYREF
  unsigned int v42; // [rsp+80h] [rbp-48h] BYREF
  __int64 v43; // [rsp+88h] [rbp-40h] BYREF
  struct _GUID v44; // [rsp+90h] [rbp-38h] BYREF

  v31 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  if ( a4 )
  {
    *a4 = 0;
    if ( !a2 )
      goto LABEL_115;
    v8 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
      v8 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IUnknown.Data4;
    if ( v8 )
    {
      if ( (bidGblFlags & 2) != 0 )
        OLEDBTraceErr(-2147217886, L"<CDBCreateCommand::CreateCommand|OLEDB|ERR> ", 0x37u);
      return 2147749410LL;
    }
    else
    {
LABEL_115:
      try
      {
        v9 = NewCM<CCCM>::CoCreateCM(a2, a2, a3, &v31);
        if ( v9 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v9, L"<CDBCreateCommand::CreateCommand|OLEDB|ERR> ", 0x45u);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v9, L"<CDBCreateCommand::CreateCommand|OLEDB|ERR> ", 0x45u);
              if ( (bidGblFlags & 2) != 0 )
                v9 = bidTraceHR(
                       off_1800C8510[0],
                       70665,
                       L"<CDBCreateCommand::CreateCommand|Trace|HR> ",
                       (unsigned int)v9);
            }
          }
          pExceptionObject = v9;
          throw (long *)&pExceptionObject;
        }
        v10 = v31;
        v11 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, CAcm **))v31->lpVtbl->QueryInterface)(
                v31,
                &IID_IService,
                &v28);
        if ( v11 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v11, L"<CDBCreateCommand::CreateCommand|OLEDB|ERR> ", 0x48u);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v11, L"<CDBCreateCommand::CreateCommand|OLEDB|ERR> ", 0x48u);
              if ( (bidGblFlags & 2) != 0 )
                v11 = bidTraceHR(
                        off_1800C8510[0],
                        73737,
                        L"<CDBCreateCommand::CreateCommand|Trace|HR> ",
                        (unsigned int)v11);
            }
          }
          v33 = v11;
          throw (long *)&v33;
        }
        v12 = v28;
        v13 = CAcm::StoreParentCMUnknown(v28, this[7]);
        if ( v13 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v13, L"<CDBCreateCommand::CreateCommand|OLEDB|ERR> ", 0x4Du);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v13, L"<CDBCreateCommand::CreateCommand|OLEDB|ERR> ", 0x4Du);
              if ( (bidGblFlags & 2) != 0 )
                v13 = bidTraceHR(
                        off_1800C8510[0],
                        78857,
                        L"<CDBCreateCommand::CreateCommand|Trace|HR> ",
                        (unsigned int)v13);
            }
          }
          v34 = v13;
          throw (long *)&v34;
        }
        v14 = this[7];
        if ( !v14 )
        {
          v15 = -2147418113;
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(-2147418113, L"<CDBCreateCommand::CreateCommand|OLEDB|ERR> ", 0x50u);
            if ( (bidGblFlags & 2) != 0 )
              v15 = bidTraceHR(off_1800C8510[0], 81929, L"<CDBCreateCommand::CreateCommand|Trace|HR> ", 2147549183LL);
          }
          v35 = v15;
          throw (long *)&v35;
        }
        v16 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v14[20];
        if ( !v16 )
        {
          v17 = -2147418113;
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(-2147418113, L"<CDBCreateCommand::CreateCommand|OLEDB|ERR> ", 0x52u);
            if ( (bidGblFlags & 2) != 0 )
              v17 = bidTraceHR(off_1800C8510[0], 83977, L"<CDBCreateCommand::CreateCommand|Trace|HR> ", 2147549183LL);
          }
          v36 = v17;
          throw (long *)&v36;
        }
        v18 = (**v16)(v16, &IID_IDBCreateCommand, &v30);
        if ( v18 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v18, L"<CDBCreateCommand::CreateCommand|OLEDB|ERR> ", 0x54u);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v18, L"<CDBCreateCommand::CreateCommand|OLEDB|ERR> ", 0x54u);
              if ( (bidGblFlags & 2) != 0 )
                v18 = bidTraceHR(
                        off_1800C8510[0],
                        86025,
                        L"<CDBCreateCommand::CreateCommand|Trace|HR> ",
                        (unsigned int)v18);
            }
          }
          v37 = v18;
          throw (long *)&v37;
        }
        v19 = (*(__int64 (__fastcall **)(__int64, CAcm *, GUID *, __int64 *))(*(_QWORD *)v30 + 24LL))(
                v30,
                v28,
                &IID_IUnknown,
                &v29);
        if ( v19 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v19, L"<CDBCreateCommand::CreateCommand|OLEDB|ERR> ", 0x56u);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v19, L"<CDBCreateCommand::CreateCommand|OLEDB|ERR> ", 0x56u);
              if ( (bidGblFlags & 2) != 0 )
                v19 = bidTraceHR(
                        off_1800C8510[0],
                        88073,
                        L"<CDBCreateCommand::CreateCommand|Trace|HR> ",
                        (unsigned int)v19);
            }
          }
          v38 = v19;
          throw (long *)&v38;
        }
        v20 = v29;
        if ( !v29 )
        {
          v21 = -2147418113;
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(-2147418113, L"<CDBCreateCommand::CreateCommand|OLEDB|ERR> ", 0x58u);
            if ( (bidGblFlags & 2) != 0 )
              v21 = bidTraceHR(off_1800C8510[0], 90121, L"<CDBCreateCommand::CreateCommand|Trace|HR> ", 2147549183LL);
          }
          v39 = v21;
          throw (long *)&v39;
        }
        v22 = *((_QWORD *)v12 + 44);
        if ( v22 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        *((_QWORD *)v12 + 44) = v20;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
        v30 = 0;
        v23 = (*(__int64 (__fastcall **)(CAcm *, __int64))(*(_QWORD *)v28 + 24LL))(v28, v29);
        if ( v23 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v23, L"<CDBCreateCommand::CreateCommand|OLEDB|ERR> ", 0x60u);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v23, L"<CDBCreateCommand::CreateCommand|OLEDB|ERR> ", 0x60u);
              if ( (bidGblFlags & 2) != 0 )
                v23 = bidTraceHR(
                        off_1800C8510[0],
                        98313,
                        L"<CDBCreateCommand::CreateCommand|Trace|HR> ",
                        (unsigned int)v23);
            }
          }
          v40 = v23;
          throw (long *)&v40;
        }
        RootAcm = CAcm::GetRootAcm((CAcm *)this[7]);
        CDPO = CDCM::GetCDPO(RootAcm);
        if ( (CDPO::GetOLEDBServices(CDPO) & 4) != 0 )
        {
          v44 = IID_ICommandProperties;
          CAcm::InsertDynamicInterface(v12, &v44);
        }
        v43 = 0;
        if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v29)(v29, &IID_ICommandText, &v43) >= 0 )
        {
          v44 = IID_ICommandText;
          CAcm::InsertDynamicInterface(v12, &v44);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
        }
        if ( a2 )
        {
          ((void (__fastcall *)(struct IUnknown *))v10->lpVtbl->AddRef)(v10);
          *a4 = v10;
        }
        else
        {
          v23 = (**(__int64 (__fastcall ***)(CAcm *, const struct _GUID *, struct IUnknown **))v28)(v28, a3, a4);
          if ( v23 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v23, L"<CDBCreateCommand::CreateCommand|OLEDB|ERR> ", 0x80u);
              if ( (bidGblFlags & 2) != 0 )
              {
                OLEDBTraceErr(v23, L"<CDBCreateCommand::CreateCommand|OLEDB|ERR> ", 0x80u);
                if ( (bidGblFlags & 2) != 0 )
                  v23 = bidTraceHR(
                          off_1800C8510[0],
                          131081,
                          L"<CDBCreateCommand::CreateCommand|Trace|HR> ",
                          (unsigned int)v23);
              }
            }
            v41 = v23;
            throw (long *)&v41;
          }
        }
        if ( v28 )
        {
          (*(void (__fastcall **)(CAcm *))(*(_QWORD *)v28 + 16LL))(v28);
          v28 = 0;
        }
        if ( v29 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
          v29 = 0;
        }
        ((void (__fastcall *)(struct IUnknown *))v10->lpVtbl->Release)(v10);
        v31 = 0;
      }
      catch ( long v42 )
      {
        if ( (bidGblFlags & 2) != 0 && off_1800C8DE8[0] )
        {
          v26 = v42;
          bidTraceA(off_1800C8510[0], 156672, off_1800C8DE8[0], v42);
        }
        else
        {
          v26 = v42;
        }
        try
        {
          v27 = v26;
          if ( *a4 )
          {
            ((void (__fastcall *)(_QWORD))(*a4)->lpVtbl->Release)(*a4);
            *a4 = 0;
          }
          if ( v30 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
            v30 = 0;
          }
          if ( v28 )
          {
            (*(void (__fastcall **)(CAcm *))(*(_QWORD *)v28 + 16LL))(v28);
            v28 = 0;
          }
          if ( v29 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
            v29 = 0;
          }
          if ( v31 )
            ((void (__fastcall *)(struct IUnknown *))v31->lpVtbl->Release)(v31);
        }
        catch ( ... )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(-2147418113, L"<CDBCreateCommand::CreateCommand|OLEDB|ERR> ", 0xADu);
            if ( (bidGblFlags & 2) != 0 )
            {
              if ( off_1800C8DE0[0] )
                bidTraceA(off_1800C8510[0], 178176, off_1800C8DE0[0], 0);
            }
          }
          v27 = -2147418113;
        }
        v23 = v27;
      }
      catch ( ... )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(-2147418113, L"<CDBCreateCommand::CreateCommand|OLEDB|ERR> ", 0xB4u);
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( off_1800C8DD8[0] )
              bidTraceA(off_1800C8510[0], 186368, off_1800C8DD8[0], 0);
          }
        }
        v23 = -2147418113;
      }
      if ( (bidGblFlags & 2) != 0 )
        return (unsigned int)bidTraceHR(
                               off_1800C8510[0],
                               191497,
                               L"<CDBCreateCommand::CreateCommand|Trace|HR> ",
                               (unsigned int)v23);
      return (unsigned int)v23;
    }
  }
  else
  {
    if ( (bidGblFlags & 2) != 0 )
      OLEDBTraceErr(-2147024809, L"<CDBCreateCommand::CreateCommand|OLEDB|ERR> ", 0x2Fu);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18001baf0  mov     rax, rsp
0x18001baf3  mov     [rax+8], rbx
0x18001baf7  mov     [rax+10h], rsi
0x18001bafb  mov     [rax+20h], r9
0x18001baff  mov     [rax+18h], r8
0x18001bb03  push    rdi
0x18001bb04  push    r12
0x18001bb06  push    r13
0x18001bb08  push    r14
0x18001bb0a  push    r15
0x18001bb0c  sub     rsp, 0A0h
0x18001bb13  mov     r14, r9
0x18001bb16  mov     r12, rdx
0x18001bb19  mov     r13, rcx
0x18001bb1c  xor     ebx, ebx
0x18001bb1e  mov     [rax-78h], rbx
0x18001bb22  mov     [rsp+0C8h+var_90], rbx
0x18001bb27  mov     [rsp+0C8h+var_88], rbx
0x18001bb2c  mov     [rax-80h], rbx
0x18001bb30  test    r9, r9
0x18001bb33  jnz     short loc_18001BB5E
0x18001bb35  mov     bl, 2
0x18001bb37  test    byte ptr cs:_bidGblFlags, bl
0x18001bb3d  jz      short loc_18001BB54
0x18001bb3f  lea     r8d, [r9+2Fh]; unsigned int
0x18001bb43  lea     rdx, aCdbcreatecomma_1; "<CDBCreateCommand::CreateCommand|OLEDB|"...
0x18001bb4a  mov     ecx, 80070057h; int
0x18001bb4f  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001bb54  mov     eax, 80070057h
0x18001bb59  jmp     loc_18001C28C
0x18001bb5e  mov     [r9], rbx
0x18001bb61  test    r12, r12
0x18001bb64  jz      short loc_18001BBAD
0x18001bb66  mov     rax, [r8]
0x18001bb69  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x18001bb70  jnz     short loc_18001BB7D
0x18001bb72  mov     rax, [r8+8]
0x18001bb76  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x18001bb7d  test    rax, rax
0x18001bb80  jz      short loc_18001BBAD
0x18001bb82  mov     bl, 2
0x18001bb84  test    byte ptr cs:_bidGblFlags, bl
0x18001bb8a  jz      short loc_18001BBA3
0x18001bb8c  mov     r8d, 37h ; '7'; unsigned int
0x18001bb92  lea     rdx, aCdbcreatecomma_1; "<CDBCreateCommand::CreateCommand|OLEDB|"...
0x18001bb99  mov     ecx, 80040E22h; int
0x18001bb9e  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001bba3  mov     eax, 80040E22h
0x18001bba8  jmp     loc_18001C28C
0x18001bbad  lea     r9, [rsp+0C8h+var_78]
0x18001bbb2  mov     rcx, r12
0x18001bbb5  call    ?CoCreateCM@?$NewCM@VCCCM@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z; NewCM<CCCM>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)
0x18001bbba  mov     edi, eax
0x18001bbbc  test    eax, eax
0x18001bbbe  jns     short loc_18001BC3A
0x18001bbc0  mov     eax, cs:_bidGblFlags
0x18001bbc6  mov     bl, 2
0x18001bbc8  test    bl, al
0x18001bbca  jz      short loc_18001BC25
0x18001bbcc  mov     r8d, 45h ; 'E'; unsigned int
0x18001bbd2  lea     rdx, aCdbcreatecomma_1; "<CDBCreateCommand::CreateCommand|OLEDB|"...
0x18001bbd9  mov     ecx, edi; int
0x18001bbdb  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001bbe0  mov     eax, cs:_bidGblFlags
0x18001bbe6  test    bl, al
0x18001bbe8  jz      short loc_18001BC25
0x18001bbea  mov     r8d, 45h ; 'E'; unsigned int
0x18001bbf0  lea     rdx, aCdbcreatecomma_1; "<CDBCreateCommand::CreateCommand|OLEDB|"...
0x18001bbf7  mov     ecx, edi; int
0x18001bbf9  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001bbfe  mov     eax, cs:_bidGblFlags
0x18001bc04  test    bl, al
0x18001bc06  jz      short loc_18001BC25
0x18001bc08  mov     r9d, edi
0x18001bc0b  lea     r8, aCdbcreatecomma_0; "<CDBCreateCommand::CreateCommand|Trace|"...
0x18001bc12  mov     edx, 11409h
0x18001bc17  mov     rcx, cs:off_1800C8510; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18001bc1e  call    _bidTraceHR
0x18001bc23  mov     edi, eax
0x18001bc25  mov     [rsp+0C8h+pExceptionObject], edi
0x18001bc29  lea     rdx, _TI1J; pThrowInfo
0x18001bc30  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x18001bc35  call    _CxxThrowException_0
0x18001bc3a  mov     rsi, [rsp+0C8h+var_78]
0x18001bc3f  mov     rax, [rsi]
0x18001bc42  lea     r8, [rsp+0C8h+var_90]
0x18001bc47  lea     rdx, IID_IService
0x18001bc4e  mov     rcx, rsi
0x18001bc51  mov     rax, [rax]
0x18001bc54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc59  mov     edi, eax
0x18001bc5b  test    eax, eax
0x18001bc5d  jns     short loc_18001BCD9
0x18001bc5f  mov     eax, cs:_bidGblFlags
0x18001bc65  mov     bl, 2
0x18001bc67  test    bl, al
0x18001bc69  jz      short loc_18001BCC4
0x18001bc6b  mov     r8d, 48h ; 'H'; unsigned int
0x18001bc71  lea     rdx, aCdbcreatecomma_1; "<CDBCreateCommand::CreateCommand|OLEDB|"...
0x18001bc78  mov     ecx, edi; int
0x18001bc7a  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001bc7f  mov     eax, cs:_bidGblFlags
0x18001bc85  test    bl, al
0x18001bc87  jz      short loc_18001BCC4
0x18001bc89  mov     r8d, 48h ; 'H'; unsigned int
0x18001bc8f  lea     rdx, aCdbcreatecomma_1; "<CDBCreateCommand::CreateCommand|OLEDB|"...
0x18001bc96  mov     ecx, edi; int
0x18001bc98  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001bc9d  mov     eax, cs:_bidGblFlags
0x18001bca3  test    bl, al
0x18001bca5  jz      short loc_18001BCC4
0x18001bca7  mov     r9d, edi
0x18001bcaa  lea     r8, aCdbcreatecomma_0; "<CDBCreateCommand::CreateCommand|Trace|"...
0x18001bcb1  mov     edx, 12009h
0x18001bcb6  mov     rcx, cs:off_1800C8510; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18001bcbd  call    _bidTraceHR
0x18001bcc2  mov     edi, eax
0x18001bcc4  mov     [rsp+0C8h+var_6C], edi
0x18001bcc8  lea     rdx, _TI1J; pThrowInfo
0x18001bccf  lea     rcx, [rsp+0C8h+var_6C]; pExceptionObject
0x18001bcd4  call    _CxxThrowException_0
0x18001bcd9  mov     r15, [rsp+0C8h+var_90]
0x18001bcde  mov     rdx, [r13+38h]; void *
0x18001bce2  mov     rcx, r15; this
0x18001bce5  call    ?StoreParentCMUnknown@CAcm@@QEAAJPEAX@Z; CAcm::StoreParentCMUnknown(void *)
0x18001bcea  mov     edi, eax
0x18001bcec  test    eax, eax
0x18001bcee  jns     short loc_18001BD6A
0x18001bcf0  mov     eax, cs:_bidGblFlags
0x18001bcf6  mov     bl, 2
0x18001bcf8  test    bl, al
0x18001bcfa  jz      short loc_18001BD55
0x18001bcfc  mov     r8d, 4Dh ; 'M'; unsigned int
0x18001bd02  lea     rdx, aCdbcreatecomma_1; "<CDBCreateCommand::CreateCommand|OLEDB|"...
0x18001bd09  mov     ecx, edi; int
0x18001bd0b  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001bd10  mov     eax, cs:_bidGblFlags
0x18001bd16  test    bl, al
0x18001bd18  jz      short loc_18001BD55
0x18001bd1a  mov     r8d, 4Dh ; 'M'; unsigned int
0x18001bd20  lea     rdx, aCdbcreatecomma_1; "<CDBCreateCommand::CreateCommand|OLEDB|"...
0x18001bd27  mov     ecx, edi; int
0x18001bd29  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001bd2e  mov     eax, cs:_bidGblFlags
0x18001bd34  test    bl, al
0x18001bd36  jz      short loc_18001BD55
0x18001bd38  mov     r9d, edi
0x18001bd3b  lea     r8, aCdbcreatecomma_0; "<CDBCreateCommand::CreateCommand|Trace|"...
0x18001bd42  mov     edx, 13409h
0x18001bd47  mov     rcx, cs:off_1800C8510; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18001bd4e  call    _bidTraceHR
0x18001bd53  mov     edi, eax
0x18001bd55  mov     [rsp+0C8h+var_68], edi
0x18001bd59  lea     rdx, _TI1J; pThrowInfo
0x18001bd60  lea     rcx, [rsp+0C8h+var_68]; pExceptionObject
0x18001bd65  call    _CxxThrowException_0
0x18001bd6a  mov     rax, [r13+38h]
0x18001bd6e  test    rax, rax
0x18001bd71  jnz     short loc_18001BDD4
0x18001bd73  mov     eax, cs:_bidGblFlags
0x18001bd79  mov     bl, 2
0x18001bd7b  mov     edi, 8000FFFFh
0x18001bd80  test    bl, al
0x18001bd82  jz      short loc_18001BDBF
0x18001bd84  mov     r8d, 50h ; 'P'; unsigned int
0x18001bd8a  lea     rdx, aCdbcreatecomma_1; "<CDBCreateCommand::CreateCommand|OLEDB|"...
0x18001bd91  mov     ecx, edi; int
0x18001bd93  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001bd98  mov     eax, cs:_bidGblFlags
0x18001bd9e  test    bl, al
0x18001bda0  jz      short loc_18001BDBF
0x18001bda2  mov     r9d, edi
0x18001bda5  lea     r8, aCdbcreatecomma_0; "<CDBCreateCommand::CreateCommand|Trace|"...
0x18001bdac  mov     edx, 14009h
0x18001bdb1  mov     rcx, cs:off_1800C8510; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18001bdb8  call    _bidTraceHR
0x18001bdbd  mov     edi, eax
0x18001bdbf  mov     [rsp+0C8h+var_64], edi
0x18001bdc3  lea     rdx, _TI1J; pThrowInfo
0x18001bdca  lea     rcx, [rsp+0C8h+var_64]; pExceptionObject
0x18001bdcf  call    _CxxThrowException_0
0x18001bdd4  mov     rcx, [rax+0A0h]
0x18001bddb  test    rcx, rcx
0x18001bdde  jnz     short loc_18001BE3F
0x18001bde0  mov     eax, cs:_bidGblFlags
0x18001bde6  mov     bl, 2
0x18001bde8  mov     edi, 8000FFFFh
0x18001bded  test    bl, al
0x18001bdef  jz      short loc_18001BE2A
0x18001bdf1  lea     r8d, [rcx+52h]; unsigned int
0x18001bdf5  lea     rdx, aCdbcreatecomma_1; "<CDBCreateCommand::CreateCommand|OLEDB|"...
0x18001bdfc  mov     ecx, edi; int
0x18001bdfe  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001be03  mov     eax, cs:_bidGblFlags
0x18001be09  test    bl, al
0x18001be0b  jz      short loc_18001BE2A
0x18001be0d  mov     r9d, edi
0x18001be10  lea     r8, aCdbcreatecomma_0; "<CDBCreateCommand::CreateCommand|Trace|"...
0x18001be17  mov     edx, 14809h
0x18001be1c  mov     rcx, cs:off_1800C8510; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18001be23  call    _bidTraceHR
0x18001be28  mov     edi, eax
0x18001be2a  mov     [rsp+0C8h+var_60], edi
0x18001be2e  lea     rdx, _TI1J; pThrowInfo
0x18001be35  lea     rcx, [rsp+0C8h+var_60]; pExceptionObject
0x18001be3a  call    _CxxThrowException_0
0x18001be3f  mov     rax, [rcx]
0x18001be42  lea     r8, [rsp+0C8h+var_80]
0x18001be47  lea     rdx, IID_IDBCreateCommand
0x18001be4e  mov     rax, [rax]
0x18001be51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be56  mov     edi, eax
0x18001be58  test    eax, eax
0x18001be5a  jns     short loc_18001BED6
0x18001be5c  mov     eax, cs:_bidGblFlags
0x18001be62  mov     bl, 2
0x18001be64  test    bl, al
0x18001be66  jz      short loc_18001BEC1
0x18001be68  mov     r8d, 54h ; 'T'; unsigned int
0x18001be6e  lea     rdx, aCdbcreatecomma_1; "<CDBCreateCommand::CreateCommand|OLEDB|"...
0x18001be75  mov     ecx, edi; int
0x18001be77  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001be7c  mov     eax, cs:_bidGblFlags
0x18001be82  test    bl, al
0x18001be84  jz      short loc_18001BEC1
0x18001be86  mov     r8d, 54h ; 'T'; unsigned int
0x18001be8c  lea     rdx, aCdbcreatecomma_1; "<CDBCreateCommand::CreateCommand|OLEDB|"...
0x18001be93  mov     ecx, edi; int
0x18001be95  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001be9a  mov     eax, cs:_bidGblFlags
0x18001bea0  test    bl, al
0x18001bea2  jz      short loc_18001BEC1
0x18001bea4  mov     r9d, edi
0x18001bea7  lea     r8, aCdbcreatecomma_0; "<CDBCreateCommand::CreateCommand|Trace|"...
0x18001beae  mov     edx, 15009h
0x18001beb3  mov     rcx, cs:off_1800C8510; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18001beba  call    _bidTraceHR
0x18001bebf  mov     edi, eax
0x18001bec1  mov     [rsp+0C8h+var_5C], edi
0x18001bec5  lea     rdx, _TI1J; pThrowInfo
0x18001becc  lea     rcx, [rsp+0C8h+var_5C]; pExceptionObject
0x18001bed1  call    _CxxThrowException_0
0x18001bed6  mov     rcx, [rsp+0C8h+var_80]
0x18001bedb  mov     rax, [rcx]
0x18001bede  lea     r9, [rsp+0C8h+var_88]
0x18001bee3  lea     r8, IID_IUnknown
0x18001beea  mov     rdx, [rsp+0C8h+var_90]
0x18001beef  mov     rax, [rax+18h]
0x18001bef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bef8  mov     edi, eax
0x18001befa  test    eax, eax
0x18001befc  jns     short loc_18001BF78
0x18001befe  mov     eax, cs:_bidGblFlags
0x18001bf04  mov     bl, 2
0x18001bf06  test    bl, al
0x18001bf08  jz      short loc_18001BF63
0x18001bf0a  mov     r8d, 56h ; 'V'; unsigned int
0x18001bf10  lea     rdx, aCdbcreatecomma_1; "<CDBCreateCommand::CreateCommand|OLEDB|"...
0x18001bf17  mov     ecx, edi; int
0x18001bf19  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001bf1e  mov     eax, cs:_bidGblFlags
0x18001bf24  test    bl, al
0x18001bf26  jz      short loc_18001BF63
0x18001bf28  mov     r8d, 56h ; 'V'; unsigned int
0x18001bf2e  lea     rdx, aCdbcreatecomma_1; "<CDBCreateCommand::CreateCommand|OLEDB|"...
0x18001bf35  mov     ecx, edi; int
0x18001bf37  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001bf3c  mov     eax, cs:_bidGblFlags
0x18001bf42  test    bl, al
0x18001bf44  jz      short loc_18001BF63
0x18001bf46  mov     r9d, edi
0x18001bf49  lea     r8, aCdbcreatecomma_0; "<CDBCreateCommand::CreateCommand|Trace|"...
0x18001bf50  mov     edx, 15809h
0x18001bf55  mov     rcx, cs:off_1800C8510; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18001bf5c  call    _bidTraceHR
0x18001bf61  mov     edi, eax
0x18001bf63  mov     [rsp+0C8h+var_58], edi
0x18001bf67  lea     rdx, _TI1J; pThrowInfo
0x18001bf6e  lea     rcx, [rsp+0C8h+var_58]; pExceptionObject
0x18001bf73  call    _CxxThrowException_0
0x18001bf78  mov     rbx, [rsp+0C8h+var_88]
0x18001bf7d  test    rbx, rbx
0x18001bf80  jnz     short loc_18001BFE3
0x18001bf82  mov     eax, cs:_bidGblFlags
0x18001bf88  mov     bl, 2
0x18001bf8a  mov     edi, 8000FFFFh
0x18001bf8f  test    bl, al
0x18001bf91  jz      short loc_18001BFCE
0x18001bf93  mov     r8d, 58h ; 'X'; unsigned int
0x18001bf99  lea     rdx, aCdbcreatecomma_1; "<CDBCreateCommand::CreateCommand|OLEDB|"...
0x18001bfa0  mov     ecx, edi; int
0x18001bfa2  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001bfa7  mov     eax, cs:_bidGblFlags
0x18001bfad  test    bl, al
0x18001bfaf  jz      short loc_18001BFCE
0x18001bfb1  mov     r9d, edi
0x18001bfb4  lea     r8, aCdbcreatecomma_0; "<CDBCreateCommand::CreateCommand|Trace|"...
0x18001bfbb  mov     edx, 16009h
0x18001bfc0  mov     rcx, cs:off_1800C8510; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18001bfc7  call    _bidTraceHR
  ... truncated ...
```
