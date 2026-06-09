# CSyncMLCmd::CreateCmd(SyncMLElemType,CSyncMLCmd *,CSyncMLDPU *,ushort const *,ulong,CSyncMLCmd * *)

- ea: `0x18001fa3c`
- end: `0x18001fed8`
- name: `?CreateCmd@CSyncMLCmd@@SAJW4SyncMLElemType@@PEAV1@PEAVCSyncMLDPU@@PEBGKPEAPEAV1@@Z`
- size: `1180`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180008620`
- `0x18000f220`

## callees

- `0x1800034d0`
- `0x1800045b0`
- `0x1800145f0`
- `0x18001e4ec`
- `0x18001e57c`
- `0x18001e5fc`
- `0x18001e654`
- `0x18001fa3c`
- `0x180030010`

## import_xrefs

- `DMCmnUtils!CopyString` at `0x18001fea9`
- `DMCmnUtils!CopyString` at `0x18001fea9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSyncMLCmd::CreateCmd(
        int a1,
        __int64 a2,
        __int64 a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        CSyncMLCmdAlert **a6)
{
  int v10; // esi
  CSyncMLCmdGet *v11; // rax
  CSyncMLCmdAlert *v12; // rax
  CSyncMLCmdAlert *v13; // rbx
  CSyncMLCmdAlert *v14; // rax
  void **v15; // rdx
  CSyncMLCmdAlert *v16; // rax
  CSyncMLCmdAlert *v17; // rax
  CSyncMLCmdAlert *v18; // rax
  CSyncMLCmdAlert *v19; // rax
  CSyncMLCmdAlert *v20; // rax
  CSyncMLCmdStatus *v21; // rax
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  CSyncMLCmdAlert *v29; // rax
  CSyncMLCmdAlert *v30; // rax
  CSyncMLCmdAlert *v31; // rax
  __int64 v32; // rcx
  CSyncMLCmdAlert *v33; // rax
  __int64 v34; // [rsp+30h] [rbp-38h] BYREF
  int v35; // [rsp+70h] [rbp+8h] BYREF

  if ( a1 > 73 )
    goto LABEL_38;
  v10 = 0;
  if ( a1 == 73 )
  {
    v33 = (CSyncMLCmdAlert *)operator new(0xA8u, (const struct std::nothrow_t *)&std::nothrow);
    v13 = v33;
    v34 = (__int64)v33;
    if ( !v33 )
      goto LABEL_50;
    CSyncMLCmd::CSyncMLCmd(v33, 73);
    *(_QWORD *)v13 = &CSyncMLCmd::`vftable';
    if ( a4 )
    {
      if ( a5 )
      {
        v10 = CopyString(a4, a5, (unsigned __int16 **)v13 + 14);
        if ( v10 < 0 )
        {
          (*(void (__fastcall **)(CSyncMLCmdAlert *, __int64))(*(_QWORD *)v13 + 40LL))(v13, 1);
          goto LABEL_39;
        }
      }
    }
  }
  else
  {
    if ( a1 > 33 )
    {
      v22 = a1 - 34;
      if ( v22 )
      {
        v23 = v22 - 1;
        if ( v23 )
        {
          v24 = v23 - 1;
          if ( !v24 )
          {
            v30 = (CSyncMLCmdAlert *)operator new(0xA8u, (const struct std::nothrow_t *)&std::nothrow);
            v13 = v30;
            v34 = (__int64)v30;
            if ( v30 )
            {
              CSyncMLCmd::CSyncMLCmd(v30, 36);
              v15 = &CSyncMLCmdReplace::`vftable';
              goto LABEL_46;
            }
            goto LABEL_48;
          }
          v25 = v24 - 1;
          if ( v25 )
          {
            v26 = v25 - 1;
            if ( v26 )
            {
              v27 = v26 - 1;
              if ( !v27 )
              {
                v29 = (CSyncMLCmdAlert *)operator new(0xB0u, (const struct std::nothrow_t *)&std::nothrow);
                v13 = v29;
                v34 = (__int64)v29;
                if ( !v29 )
                  goto LABEL_48;
                CSyncMLCmd::CSyncMLCmd(v29, 39);
                v15 = &CSyncMLCmdSequence::`vftable';
                *((_DWORD *)v13 + 42) = -1;
                goto LABEL_24;
              }
              if ( v27 != 1 )
                goto LABEL_38;
            }
          }
        }
      }
    }
    else if ( a1 != 33 )
    {
      switch ( a1 )
      {
        case 25:
          v21 = (CSyncMLCmdStatus *)operator new(0xD8u, (const struct std::nothrow_t *)&std::nothrow);
          v34 = (__int64)v21;
          if ( v21 )
          {
            v12 = CSyncMLCmdStatus::CSyncMLCmdStatus(v21);
            goto LABEL_15;
          }
          goto LABEL_48;
        case 26:
          v20 = (CSyncMLCmdAlert *)operator new(0xA8u, (const struct std::nothrow_t *)&std::nothrow);
          v13 = v20;
          v34 = (__int64)v20;
          if ( v20 )
          {
            CSyncMLCmd::CSyncMLCmd(v20, 26);
            v15 = &CSyncMLCmdAdd::`vftable';
            goto LABEL_46;
          }
          goto LABEL_48;
        case 27:
          v19 = (CSyncMLCmdAlert *)operator new(0xD8u, (const struct std::nothrow_t *)&std::nothrow);
          v34 = (__int64)v19;
          if ( v19 )
          {
            v12 = CSyncMLCmdAlert::CSyncMLCmdAlert(v19);
            goto LABEL_15;
          }
          goto LABEL_48;
      }
      if ( a1 != 28 )
      {
        switch ( a1 )
        {
          case 29:
            v17 = (CSyncMLCmdAlert *)operator new(0xA8u, (const struct std::nothrow_t *)&std::nothrow);
            v13 = v17;
            v34 = (__int64)v17;
            if ( v17 )
            {
              CSyncMLCmd::CSyncMLCmd(v17, 29);
              v15 = &CSyncMLCmdCopy::`vftable';
              goto LABEL_46;
            }
            break;
          case 30:
            v16 = (CSyncMLCmdAlert *)operator new(0xA8u, (const struct std::nothrow_t *)&std::nothrow);
            v13 = v16;
            v34 = (__int64)v16;
            if ( v16 )
            {
              CSyncMLCmd::CSyncMLCmd(v16, 30);
              v15 = &CSyncMLCmdDelete::`vftable';
              goto LABEL_46;
            }
            break;
          case 31:
            v14 = (CSyncMLCmdAlert *)operator new(0xB0u, (const struct std::nothrow_t *)&std::nothrow);
            v13 = v14;
            v34 = (__int64)v14;
            if ( v14 )
            {
              CSyncMLCmd::CSyncMLCmd(v14, 31);
              v15 = &CSyncMLCmdExec::`vftable';
              *((_QWORD *)v13 + 21) = 0;
LABEL_46:
              *((_QWORD *)v13 + 20) = 0;
              *((_DWORD *)v13 + 39) = -1;
              *((_DWORD *)v13 + 38) = 1;
              goto LABEL_47;
            }
            break;
          case 32:
            v11 = (CSyncMLCmdGet *)operator new(0xC0u, (const struct std::nothrow_t *)&std::nothrow);
            v34 = (__int64)v11;
            if ( v11 )
            {
              v12 = CSyncMLCmdGet::CSyncMLCmdGet(v11);
LABEL_15:
              v13 = v12;
              goto LABEL_49;
            }
            break;
          default:
LABEL_38:
            v10 = -2147024809;
            goto LABEL_39;
        }
LABEL_48:
        v13 = 0;
LABEL_49:
        if ( !v13 )
        {
LABEL_50:
          v10 = -2147024882;
          goto LABEL_39;
        }
        goto LABEL_55;
      }
      v18 = (CSyncMLCmdAlert *)operator new(0xA8u, (const struct std::nothrow_t *)&std::nothrow);
      v13 = v18;
      v34 = (__int64)v18;
      if ( !v18 )
        goto LABEL_48;
      CSyncMLCmd::CSyncMLCmd(v18, 28);
      v15 = &CSyncMLCmdAtomic::`vftable';
LABEL_24:
      *((_QWORD *)v13 + 19) = 0;
      *((_DWORD *)v13 + 40) = 0;
      *((_DWORD *)v13 + 41) = 1;
LABEL_47:
      *(_QWORD *)v13 = v15;
      goto LABEL_49;
    }
    v31 = (CSyncMLCmdAlert *)operator new(0xA8u, (const struct std::nothrow_t *)&std::nothrow);
    v13 = v31;
    v34 = (__int64)v31;
    if ( !v31 )
      goto LABEL_50;
    CSyncMLCmd::CSyncMLCmd(v31, (unsigned int)a1);
    *(_QWORD *)v13 = &CSyncMLCmd::`vftable';
  }
  if ( *((int *)v13 + 14) >= 0 )
    *((_DWORD *)v13 + 14) = -2102788095;
LABEL_55:
  *((_QWORD *)v13 + 17) = a2;
  if ( *((_QWORD *)v13 + 10) != a3 )
  {
    v34 = a3;
    Microsoft::WRL::ComPtr<CSyncMLDPU>::InternalAddRef(&v34);
    v32 = *((_QWORD *)v13 + 10);
    *((_QWORD *)v13 + 10) = a3;
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
  *a6 = v13;
LABEL_39:
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v35 = v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18003E048,
      (unsigned __int8 *)word_180036E3A,
      a3,
      (__int64)a4,
      (__int64)&v35);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001fa3c  mov     [rsp+arg_8], rbx
0x18001fa41  mov     [rsp+arg_10], rbp
0x18001fa46  push    rsi
0x18001fa47  push    rdi
0x18001fa48  push    r12
0x18001fa4a  push    r14
0x18001fa4c  push    r15
0x18001fa4e  sub     rsp, 40h
0x18001fa52  mov     rbp, r9
0x18001fa55  mov     r14, r8
0x18001fa58  mov     r15, rdx
0x18001fa5b  mov     edi, ecx
0x18001fa5d  cmp     ecx, 49h ; 'I'
0x18001fa60  jg      loc_18001FCCC
0x18001fa66  xor     r12d, r12d
0x18001fa69  mov     esi, r12d
0x18001fa6c  cmp     ecx, 49h ; 'I'
0x18001fa6f  jz      loc_18001FE48
0x18001fa75  cmp     ecx, 21h ; '!'
0x18001fa78  jg      loc_18001FC91
0x18001fa7e  jz      loc_18001FDBE
0x18001fa84  sub     edi, 19h
0x18001fa87  jz      loc_18001FC65
0x18001fa8d  sub     edi, 1
0x18001fa90  jz      loc_18001FC2A
0x18001fa96  sub     edi, 1
0x18001fa99  jz      loc_18001FBFE
0x18001fa9f  sub     edi, 1
0x18001faa2  jz      loc_18001FBAB
0x18001faa8  sub     edi, 1
0x18001faab  jz      loc_18001FB70
0x18001fab1  sub     edi, 1
0x18001fab4  jz      short loc_18001FB35
0x18001fab6  sub     edi, 1
0x18001fab9  jz      short loc_18001FAF3
0x18001fabb  cmp     edi, 1
0x18001fabe  jnz     loc_18001FCCC
0x18001fac4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001facb  mov     ecx, 0C0h; unsigned __int64
0x18001fad0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001fad5  mov     [rsp+68h+var_38], rax
0x18001fada  test    rax, rax
0x18001fadd  jz      loc_18001FDAC
0x18001fae3  mov     rcx, rax; this
0x18001fae6  call    ??0CSyncMLCmdGet@@QEAA@XZ; CSyncMLCmdGet::CSyncMLCmdGet(void)
0x18001faeb  mov     rbx, rax
0x18001faee  jmp     loc_18001FDAF
0x18001faf3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fafa  mov     ecx, 0B0h; unsigned __int64
0x18001faff  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001fb04  mov     rbx, rax
0x18001fb07  mov     [rsp+68h+var_38], rax
0x18001fb0c  test    rax, rax
0x18001fb0f  jz      loc_18001FDAC
0x18001fb15  mov     edx, 1Fh
0x18001fb1a  mov     rcx, rax
0x18001fb1d  call    ??0CSyncMLCmd@@IEAA@W4SyncMLElemType@@@Z; CSyncMLCmd::CSyncMLCmd(SyncMLElemType)
0x18001fb22  lea     rdx, ??_7CSyncMLCmdExec@@6B@; const CSyncMLCmdExec::`vftable'
0x18001fb29  mov     [rbx+0A8h], r12
0x18001fb30  jmp     loc_18001FD8C
0x18001fb35  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fb3c  mov     ecx, 0A8h; unsigned __int64
0x18001fb41  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001fb46  mov     rbx, rax
0x18001fb49  mov     [rsp+68h+var_38], rax
0x18001fb4e  test    rax, rax
0x18001fb51  jz      loc_18001FDAC
0x18001fb57  mov     edx, 1Eh
0x18001fb5c  mov     rcx, rax
0x18001fb5f  call    ??0CSyncMLCmd@@IEAA@W4SyncMLElemType@@@Z; CSyncMLCmd::CSyncMLCmd(SyncMLElemType)
0x18001fb64  lea     rdx, ??_7CSyncMLCmdDelete@@6B@; const CSyncMLCmdDelete::`vftable'
0x18001fb6b  jmp     loc_18001FD8C
0x18001fb70  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fb77  mov     ecx, 0A8h; unsigned __int64
0x18001fb7c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001fb81  mov     rbx, rax
0x18001fb84  mov     [rsp+68h+var_38], rax
0x18001fb89  test    rax, rax
0x18001fb8c  jz      loc_18001FDAC
0x18001fb92  mov     edx, 1Dh
0x18001fb97  mov     rcx, rax
0x18001fb9a  call    ??0CSyncMLCmd@@IEAA@W4SyncMLElemType@@@Z; CSyncMLCmd::CSyncMLCmd(SyncMLElemType)
0x18001fb9f  lea     rdx, ??_7CSyncMLCmdCopy@@6B@; const CSyncMLCmdCopy::`vftable'
0x18001fba6  jmp     loc_18001FD8C
0x18001fbab  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fbb2  mov     ecx, 0A8h; unsigned __int64
0x18001fbb7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001fbbc  mov     rbx, rax
0x18001fbbf  mov     [rsp+68h+var_38], rax
0x18001fbc4  test    rax, rax
0x18001fbc7  jz      loc_18001FDAC
0x18001fbcd  mov     edx, 1Ch
0x18001fbd2  mov     rcx, rax
0x18001fbd5  call    ??0CSyncMLCmd@@IEAA@W4SyncMLElemType@@@Z; CSyncMLCmd::CSyncMLCmd(SyncMLElemType)
0x18001fbda  lea     rdx, ??_7CSyncMLCmdAtomic@@6B@; const CSyncMLCmdAtomic::`vftable'
0x18001fbe1  mov     [rbx+98h], r12
0x18001fbe8  mov     [rbx+0A0h], r12d
0x18001fbef  mov     dword ptr [rbx+0A4h], 1
0x18001fbf9  jmp     loc_18001FDA7
0x18001fbfe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fc05  mov     ecx, 0D8h; unsigned __int64
0x18001fc0a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001fc0f  mov     [rsp+68h+var_38], rax
0x18001fc14  test    rax, rax
0x18001fc17  jz      loc_18001FDAC
0x18001fc1d  mov     rcx, rax; this
0x18001fc20  call    ??0CSyncMLCmdAlert@@QEAA@XZ; CSyncMLCmdAlert::CSyncMLCmdAlert(void)
0x18001fc25  jmp     loc_18001FAEB
0x18001fc2a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fc31  mov     ecx, 0A8h; unsigned __int64
0x18001fc36  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001fc3b  mov     rbx, rax
0x18001fc3e  mov     [rsp+68h+var_38], rax
0x18001fc43  test    rax, rax
0x18001fc46  jz      loc_18001FDAC
0x18001fc4c  mov     edx, 1Ah
0x18001fc51  mov     rcx, rax
0x18001fc54  call    ??0CSyncMLCmd@@IEAA@W4SyncMLElemType@@@Z; CSyncMLCmd::CSyncMLCmd(SyncMLElemType)
0x18001fc59  lea     rdx, ??_7CSyncMLCmdAdd@@6B@; const CSyncMLCmdAdd::`vftable'
0x18001fc60  jmp     loc_18001FD8C
0x18001fc65  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fc6c  mov     ecx, 0D8h; unsigned __int64
0x18001fc71  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001fc76  mov     [rsp+68h+var_38], rax
0x18001fc7b  test    rax, rax
0x18001fc7e  jz      loc_18001FDAC
0x18001fc84  mov     rcx, rax; this
0x18001fc87  call    ??0CSyncMLCmdStatus@@QEAA@XZ; CSyncMLCmdStatus::CSyncMLCmdStatus(void)
0x18001fc8c  jmp     loc_18001FAEB
0x18001fc91  sub     ecx, 22h ; '"'
0x18001fc94  jz      loc_18001FDBE
0x18001fc9a  sub     ecx, 1
0x18001fc9d  jz      loc_18001FDBE
0x18001fca3  sub     ecx, 1
0x18001fca6  jz      loc_18001FD5A
0x18001fcac  sub     ecx, 1
0x18001fcaf  jz      loc_18001FDBE
0x18001fcb5  sub     ecx, 1
0x18001fcb8  jz      loc_18001FDBE
0x18001fcbe  sub     ecx, 1
0x18001fcc1  jz      short loc_18001FD19
0x18001fcc3  cmp     ecx, 1
0x18001fcc6  jz      loc_18001FDBE
0x18001fccc  mov     esi, 80070057h
0x18001fcd1  mov     eax, cs:dword_18003E048
0x18001fcd7  cmp     eax, 5
0x18001fcda  jbe     short loc_18001FCFD
0x18001fcdc  mov     [rsp+68h+arg_0], esi
0x18001fce0  lea     rax, [rsp+68h+arg_0]
0x18001fce5  mov     [rsp+68h+var_48], rax
0x18001fcea  lea     rdx, word_180036E3A
0x18001fcf1  lea     rcx, dword_18003E048
0x18001fcf8  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001fcfd  mov     eax, esi
0x18001fcff  lea     r11, [rsp+68h+var_28]
0x18001fd04  mov     rbx, [r11+38h]
0x18001fd08  mov     rbp, [r11+40h]
0x18001fd0c  mov     rsp, r11
0x18001fd0f  pop     r15
0x18001fd11  pop     r14
0x18001fd13  pop     r12
0x18001fd15  pop     rdi
0x18001fd16  pop     rsi
0x18001fd17  retn
0x18001fd19  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fd20  mov     ecx, 0B0h; unsigned __int64
0x18001fd25  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001fd2a  mov     rbx, rax
0x18001fd2d  mov     [rsp+68h+var_38], rax
0x18001fd32  test    rax, rax
0x18001fd35  jz      short loc_18001FDAC
0x18001fd37  mov     edx, 27h ; '''
0x18001fd3c  mov     rcx, rax
0x18001fd3f  call    ??0CSyncMLCmd@@IEAA@W4SyncMLElemType@@@Z; CSyncMLCmd::CSyncMLCmd(SyncMLElemType)
0x18001fd44  lea     rdx, ??_7CSyncMLCmdSequence@@6B@; const CSyncMLCmdSequence::`vftable'
0x18001fd4b  mov     dword ptr [rbx+0A8h], 0FFFFFFFFh
0x18001fd55  jmp     loc_18001FBE1
0x18001fd5a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fd61  mov     ecx, 0A8h; unsigned __int64
0x18001fd66  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001fd6b  mov     rbx, rax
0x18001fd6e  mov     [rsp+68h+var_38], rax
0x18001fd73  test    rax, rax
0x18001fd76  jz      short loc_18001FDAC
0x18001fd78  mov     edx, 24h ; '$'
0x18001fd7d  mov     rcx, rax
0x18001fd80  call    ??0CSyncMLCmd@@IEAA@W4SyncMLElemType@@@Z; CSyncMLCmd::CSyncMLCmd(SyncMLElemType)
0x18001fd85  lea     rdx, ??_7CSyncMLCmdReplace@@6B@; const CSyncMLCmdReplace::`vftable'
0x18001fd8c  mov     [rbx+0A0h], r12
0x18001fd93  mov     dword ptr [rbx+9Ch], 0FFFFFFFFh
0x18001fd9d  mov     dword ptr [rbx+98h], 1
0x18001fda7  mov     [rbx], rdx
0x18001fdaa  jmp     short loc_18001FDAF
0x18001fdac  mov     rbx, r12
0x18001fdaf  test    rbx, rbx
0x18001fdb2  jnz     short loc_18001FE02
0x18001fdb4  mov     esi, 8007000Eh
0x18001fdb9  jmp     loc_18001FCD1
0x18001fdbe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fdc5  mov     ecx, 0A8h; unsigned __int64
0x18001fdca  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001fdcf  mov     rbx, rax
0x18001fdd2  mov     [rsp+68h+var_38], rax
0x18001fdd7  test    rax, rax
0x18001fdda  jz      short loc_18001FDB4
0x18001fddc  mov     edx, edi
0x18001fdde  mov     rcx, rax
0x18001fde1  call    ??0CSyncMLCmd@@IEAA@W4SyncMLElemType@@@Z; CSyncMLCmd::CSyncMLCmd(SyncMLElemType)
0x18001fde6  lea     rdx, ??_7CSyncMLCmd@@6B@; const CSyncMLCmd::`vftable'
0x18001fded  mov     [rbx], rdx
0x18001fdf0  test    rbx, rbx
0x18001fdf3  jz      short loc_18001FDB4
0x18001fdf5  cmp     [rbx+38h], r12d
0x18001fdf9  jl      short loc_18001FE02
0x18001fdfb  mov     dword ptr [rbx+38h], 82AA0001h
0x18001fe02  mov     [rbx+88h], r15
0x18001fe09  cmp     [rbx+50h], r14
0x18001fe0d  jz      short loc_18001FE38
0x18001fe0f  mov     [rsp+68h+var_38], r14
0x18001fe14  lea     rcx, [rsp+68h+var_38]
0x18001fe19  call    ?InternalAddRef@?$ComPtr@VCSyncMLDPU@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<CSyncMLDPU>::InternalAddRef(void)
0x18001fe1e  mov     rcx, [rbx+50h]
0x18001fe22  mov     [rbx+50h], r14
0x18001fe26  test    rcx, rcx
0x18001fe29  jz      short loc_18001FE38
0x18001fe2b  mov     rax, [rcx]
0x18001fe2e  mov     rax, [rax+10h]
0x18001fe32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe37  nop
0x18001fe38  mov     rax, [rsp+68h+arg_28]
0x18001fe40  mov     [rax], rbx
0x18001fe43  jmp     loc_18001FCD1
0x18001fe48  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fe4f  mov     ecx, 0A8h; unsigned __int64
0x18001fe54  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001fe59  mov     rbx, rax
0x18001fe5c  mov     [rsp+68h+var_38], rax
0x18001fe61  test    rax, rax
0x18001fe64  jz      loc_18001FDB4
0x18001fe6a  mov     edx, 49h ; 'I'
0x18001fe6f  mov     rcx, rax
0x18001fe72  call    ??0CSyncMLCmd@@IEAA@W4SyncMLElemType@@@Z; CSyncMLCmd::CSyncMLCmd(SyncMLElemType)
0x18001fe77  lea     rdx, ??_7CSyncMLCmd@@6B@; const CSyncMLCmd::`vftable'
0x18001fe7e  mov     [rbx], rdx
0x18001fe81  test    rbx, rbx
0x18001fe84  jz      loc_18001FDB4
0x18001fe8a  test    rbp, rbp
0x18001fe8d  jz      loc_18001FDF5
0x18001fe93  mov     edx, [rsp+68h+arg_20]
0x18001fe9a  test    edx, edx
0x18001fe9c  jz      loc_18001FDF5
0x18001fea2  lea     r8, [rbx+70h]
0x18001fea6  mov     rcx, rbp
0x18001fea9  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18001feb0  nop     dword ptr [rax+rax+00h]
0x18001feb5  mov     esi, eax
0x18001feb7  test    eax, eax
0x18001feb9  jns     loc_18001FDF5
0x18001febf  mov     rcx, [rbx]
0x18001fec2  mov     rax, [rcx+28h]
0x18001fec6  mov     edx, 1
0x18001fecb  mov     rcx, rbx
0x18001fece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fed3  jmp     loc_18001FCD1
```
