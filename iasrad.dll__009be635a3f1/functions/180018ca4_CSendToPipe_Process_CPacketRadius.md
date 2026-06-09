# CSendToPipe::Process(CPacketRadius *)

- ea: `0x180018ca4`
- end: `0x180019061`
- name: `?Process@CSendToPipe@@QEAAJPEAVCPacketRadius@@@Z`
- size: `957`
- prototype: `__int64 __fastcall(CSendToPipe *__hidden this, struct CPacketRadius *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180016844`

## callees

- `0x1800094e4`
- `0x1800145ec`
- `0x180018bb8`
- `0x180018ca4`
- `0x180019068`
- `0x180019340`
- `0x18001ccc0`
- `0x18001d31c`
- `0x180030010`

## string_xrefs

- `0x180018d38`: `Unable to create a Request object from class factory before sending request to backend`

## pseudocode

```c
__int64 __fastcall CSendToPipe::Process(CSendToPipe *this, struct CPacketRadius *a2)
{
  __int64 v4; // rsi
  int v5; // ebx
  __int64 v6; // rdx
  unsigned int v7; // r12d
  unsigned int v8; // r15d
  __int64 v9; // r13
  int v10; // eax
  CSendToPipe *v11; // rcx
  int v13; // [rsp+20h] [rbp-48h]
  struct IAttributesRaw *v14; // [rsp+70h] [rbp+8h] BYREF
  struct IRequest *v15; // [rsp+80h] [rbp+18h] BYREF
  __int64 v16; // [rsp+88h] [rbp+20h]

  v15 = 0;
  v14 = 0;
  v16 = *((_QWORD *)this + 2);
  v4 = v16;
  if ( !v16 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Unable to send request to backend as request handler unavailable");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_705ec960347a326cbcb5a6c0ff8f7767_Traceguids, "NPSRAD");
    }
    v5 = -2147467259;
    goto LABEL_42;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
  v5 = CSendToPipe::CreateReqInstance(this, &v15);
  v13 = v5;
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Unable to create a Request object from class factory before sending request to backend");
      v6 = 11;
LABEL_7:
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, WPP_705ec960347a326cbcb5a6c0ff8f7767_Traceguids, "NPSRAD");
      goto LABEL_42;
    }
    goto LABEL_42;
  }
  v7 = **((unsigned __int8 **)a2 + 3);
  v8 = *((_DWORD *)a2 + 22) + 8;
  if ( *((_DWORD *)a2 + 22) == -8 )
  {
LABEL_19:
    v5 = CSendToPipe::SetRequestProperties(this, v15, a2, v7, v13);
    if ( v5 >= 0 )
    {
      v10 = VSAFilter::radiusToIAS(*((VSAFilter **)this + 4), v14);
      v5 = v10;
      if ( v10 >= 0 )
      {
        if ( (int)CSendToPipe::TraceNapAttributes(v11, v14) < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WppDbgPrint("Unable to trace NAP attribute to request object before sending request to backend");
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_705ec960347a326cbcb5a6c0ff8f7767_Traceguids, "NPSRAD");
        }
        v5 = (*(__int64 (__fastcall **)(__int64, struct IRequest *))(*(_QWORD *)v4 + 56LL))(v4, v15);
        if ( v5 < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WppDbgPrint("Unable to send request object to backend");
          v6 = 16;
          goto LABEL_7;
        }
      }
      else
      {
        if ( v10 == -2147024809 )
        {
          CPacketRadius::reportMalformed(a2);
          v5 = -1073741801;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WppDbgPrint("Unable to convert Radius VSAs to IAS attributes in request object before sending it to backend");
          v6 = 14;
          goto LABEL_7;
        }
      }
    }
    goto LABEL_42;
  }
  v9 = *((_QWORD *)a2 + 2);
  v5 = ((__int64 (__fastcall *)(struct IRequest *, GUID *, struct IAttributesRaw **))v15->lpVtbl->QueryInterface)(
         v15,
         &GUID_6bc096a8_0ce6_11d1_baae_00c04fc2e20d,
         &v14);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(struct IAttributesRaw *, _QWORD, __int64))(*(_QWORD *)v14 + 24LL))(v14, v8, v9);
    v13 = v5;
    if ( v5 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("Unable to add Attributes to request object before sending request to backend");
        v6 = 13;
        goto LABEL_7;
      }
      goto LABEL_42;
    }
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Unable to obtain Attributes interface in request object before sending request to backend");
    v6 = 12;
    goto LABEL_7;
  }
LABEL_42:
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( v14 )
    (*(void (__fastcall **)(struct IAttributesRaw *))(*(_QWORD *)v14 + 16LL))(v14);
  if ( v15 )
    ((void (__fastcall *)(struct IRequest *))v15->lpVtbl->Release)(v15);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180018ca4  mov     rax, rsp
0x180018ca7  push    rbx
0x180018ca8  push    rsi
0x180018ca9  push    rdi
0x180018caa  push    r12
0x180018cac  push    r13
0x180018cae  push    r14
0x180018cb0  push    r15
0x180018cb2  sub     rsp, 30h
0x180018cb6  mov     rdi, rdx
0x180018cb9  mov     r14, rcx
0x180018cbc  mov     qword ptr [rax+18h], 0
0x180018cc4  mov     qword ptr [rax+8], 0
0x180018ccc  mov     rsi, [rcx+10h]
0x180018cd0  mov     [rsp+68h+arg_18], rsi
0x180018cd8  test    rsi, rsi
0x180018cdb  jz      loc_180018FB2
0x180018ce1  mov     rax, [rsi]
0x180018ce4  mov     rcx, rsi
0x180018ce7  mov     rax, [rax+8]
0x180018ceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018cf0  lea     rdx, [rsp+68h+arg_10]; struct IRequest **
0x180018cf8  mov     rcx, r14; this
0x180018cfb  call    ?CreateReqInstance@CSendToPipe@@QEAAJPEAPEAUIRequest@@@Z; CSendToPipe::CreateReqInstance(IRequest * *)
0x180018d00  mov     ebx, eax
0x180018d02  mov     [rsp+68h+var_48], eax
0x180018d06  test    eax, eax
0x180018d08  jns     short loc_180018D6C
0x180018d0a  lea     rdi, WPP_GLOBAL_Control
0x180018d11  mov     rax, cs:WPP_GLOBAL_Control
0x180018d18  cmp     rax, rdi
0x180018d1b  jz      loc_18001900C
0x180018d21  cmp     byte ptr [rax+19h], 2
0x180018d25  jb      loc_18001900C
0x180018d2b  test    dword ptr [rax+1Ch], 100h
0x180018d32  jz      loc_18001900C
0x180018d38  lea     rcx, aUnableToCreate_12; "Unable to create a Request object from "...
0x180018d3f  call    WppDbgPrint
0x180018d44  mov     edx, 0Bh
0x180018d49  lea     r9, aNpsrad; "NPSRAD"
0x180018d50  lea     r8, WPP_705ec960347a326cbcb5a6c0ff8f7767_Traceguids
0x180018d57  mov     rcx, cs:WPP_GLOBAL_Control
0x180018d5e  mov     rcx, [rcx+10h]
0x180018d62  call    WPP_SF_s
0x180018d67  jmp     loc_18001900C
0x180018d6c  mov     rax, [rdi+18h]
0x180018d70  movzx   r12d, byte ptr [rax]
0x180018d74  mov     r15d, [rdi+58h]
0x180018d78  add     r15d, 8
0x180018d7c  jz      loc_180018E58
0x180018d82  mov     r13, [rdi+10h]
0x180018d86  mov     rcx, [rsp+68h+arg_10]
0x180018d8e  mov     rax, [rcx]
0x180018d91  lea     r8, [rsp+68h+arg_0]
0x180018d96  lea     rdx, _GUID_6bc096a8_0ce6_11d1_baae_00c04fc2e20d
0x180018d9d  mov     rax, [rax]
0x180018da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018da5  mov     ebx, eax
0x180018da7  mov     [rsp+68h+var_48], eax
0x180018dab  test    eax, eax
0x180018dad  jns     short loc_180018DF3
0x180018daf  lea     rdi, WPP_GLOBAL_Control
0x180018db6  mov     rax, cs:WPP_GLOBAL_Control
0x180018dbd  cmp     rax, rdi
0x180018dc0  jz      loc_18001900C
0x180018dc6  cmp     byte ptr [rax+19h], 2
0x180018dca  jb      loc_18001900C
0x180018dd0  test    dword ptr [rax+1Ch], 100h
0x180018dd7  jz      loc_18001900C
0x180018ddd  lea     rcx, aUnableToObtain_6; "Unable to obtain Attributes interface i"...
0x180018de4  call    WppDbgPrint
0x180018de9  mov     edx, 0Ch
0x180018dee  jmp     loc_180018D49
0x180018df3  mov     rcx, [rsp+68h+arg_0]
0x180018df8  mov     rax, [rcx]
0x180018dfb  mov     r8, r13
0x180018dfe  mov     edx, r15d
0x180018e01  mov     rax, [rax+18h]
0x180018e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e0a  mov     ebx, eax
0x180018e0c  mov     [rsp+68h+var_48], eax
0x180018e10  test    eax, eax
0x180018e12  jns     short loc_180018E58
0x180018e14  lea     rdi, WPP_GLOBAL_Control
0x180018e1b  mov     rax, cs:WPP_GLOBAL_Control
0x180018e22  cmp     rax, rdi
0x180018e25  jz      loc_18001900C
0x180018e2b  cmp     byte ptr [rax+19h], 2
0x180018e2f  jb      loc_18001900C
0x180018e35  test    dword ptr [rax+1Ch], 100h
0x180018e3c  jz      loc_18001900C
0x180018e42  lea     rcx, aUnableToAddAtt; "Unable to add Attributes to request obj"...
0x180018e49  call    WppDbgPrint
0x180018e4e  mov     edx, 0Dh
0x180018e53  jmp     loc_180018D49
0x180018e58  mov     r9d, r12d
0x180018e5b  mov     r8, rdi
0x180018e5e  mov     rdx, [rsp+68h+arg_10]
0x180018e66  mov     rcx, r14
0x180018e69  call    ?SetRequestProperties@CSendToPipe@@AEAAJPEAUIRequest@@PEAVCPacketRadius@@W4_packettype_@@@Z; CSendToPipe::SetRequestProperties(IRequest *,CPacketRadius *,_packettype_)
0x180018e6e  mov     ebx, eax
0x180018e70  mov     [rsp+68h+var_48], eax
0x180018e74  test    eax, eax
0x180018e76  js      loc_18001900C
0x180018e7c  mov     rdx, [rsp+68h+arg_0]; struct IAttributesRaw *
0x180018e81  mov     rcx, [r14+20h]; this
0x180018e85  call    ?radiusToIAS@VSAFilter@@QEBAJPEAUIAttributesRaw@@@Z; VSAFilter::radiusToIAS(IAttributesRaw *)
0x180018e8a  mov     ebx, eax
0x180018e8c  mov     [rsp+68h+var_48], eax
0x180018e90  test    eax, eax
0x180018e92  jns     short loc_180018EF0
0x180018e94  cmp     eax, 80070057h
0x180018e99  jnz     short loc_180018EAC
0x180018e9b  mov     rcx, rdi; this
0x180018e9e  call    ?reportMalformed@CPacketRadius@@QEBAXXZ; CPacketRadius::reportMalformed(void)
0x180018ea3  mov     ebx, 0C0000017h
0x180018ea8  mov     [rsp+68h+var_48], ebx
0x180018eac  lea     rdi, WPP_GLOBAL_Control
0x180018eb3  mov     rax, cs:WPP_GLOBAL_Control
0x180018eba  cmp     rax, rdi
0x180018ebd  jz      loc_18001900C
0x180018ec3  cmp     byte ptr [rax+19h], 2
0x180018ec7  jb      loc_18001900C
0x180018ecd  test    dword ptr [rax+1Ch], 100h
0x180018ed4  jz      loc_18001900C
0x180018eda  lea     rcx, aUnableToConver_1; "Unable to convert Radius VSAs to IAS at"...
0x180018ee1  call    WppDbgPrint
0x180018ee6  mov     edx, 0Eh
0x180018eeb  jmp     loc_180018D49
0x180018ef0  mov     rdx, [rsp+68h+arg_0]; struct IAttributesRaw *
0x180018ef5  call    ?TraceNapAttributes@CSendToPipe@@QEAAJPEAUIAttributesRaw@@@Z; CSendToPipe::TraceNapAttributes(IAttributesRaw *)
0x180018efa  mov     [rsp+68h+var_48], eax
0x180018efe  test    eax, eax
0x180018f00  jns     short loc_180018F55
0x180018f02  lea     rdi, WPP_GLOBAL_Control
0x180018f09  mov     rax, cs:WPP_GLOBAL_Control
0x180018f10  cmp     rax, rdi
0x180018f13  jz      short loc_180018F5C
0x180018f15  cmp     byte ptr [rax+19h], 2
0x180018f19  jb      short loc_180018F5C
0x180018f1b  test    dword ptr [rax+1Ch], 100h
0x180018f22  jz      short loc_180018F5C
0x180018f24  lea     rcx, aUnableToTraceN; "Unable to trace NAP attribute to reques"...
0x180018f2b  call    WppDbgPrint
0x180018f30  mov     edx, 0Fh
0x180018f35  lea     r9, aNpsrad; "NPSRAD"
0x180018f3c  lea     r8, WPP_705ec960347a326cbcb5a6c0ff8f7767_Traceguids
0x180018f43  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f4a  mov     rcx, [rcx+10h]
0x180018f4e  call    WPP_SF_s
0x180018f53  jmp     short loc_180018F5C
0x180018f55  lea     rdi, WPP_GLOBAL_Control
0x180018f5c  mov     rax, [rsi]
0x180018f5f  mov     rdx, [rsp+68h+arg_10]
0x180018f67  mov     rcx, rsi
0x180018f6a  mov     rax, [rax+38h]
0x180018f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f73  mov     ebx, eax
0x180018f75  mov     [rsp+68h+var_48], eax
0x180018f79  test    eax, eax
0x180018f7b  jns     loc_18001900C
0x180018f81  mov     rax, cs:WPP_GLOBAL_Control
0x180018f88  cmp     rax, rdi
0x180018f8b  jz      short loc_18001900C
0x180018f8d  cmp     byte ptr [rax+19h], 2
0x180018f91  jb      short loc_18001900C
0x180018f93  test    dword ptr [rax+1Ch], 100h
0x180018f9a  jz      short loc_18001900C
0x180018f9c  lea     rcx, aUnableToSendRe_0; "Unable to send request object to backen"...
0x180018fa3  call    WppDbgPrint
0x180018fa8  mov     edx, 10h
0x180018fad  jmp     loc_180018D49
0x180018fb2  lea     rdi, WPP_GLOBAL_Control
0x180018fb9  mov     rax, cs:WPP_GLOBAL_Control
0x180018fc0  cmp     rax, rdi
0x180018fc3  jz      short loc_180019003
0x180018fc5  cmp     byte ptr [rax+19h], 2
0x180018fc9  jb      short loc_180019003
0x180018fcb  test    dword ptr [rax+1Ch], 100h
0x180018fd2  jz      short loc_180019003
0x180018fd4  lea     rcx, aUnableToSendRe; "Unable to send request to backend as re"...
0x180018fdb  call    WppDbgPrint
0x180018fe0  mov     edx, 0Ah
0x180018fe5  lea     r9, aNpsrad; "NPSRAD"
0x180018fec  lea     r8, WPP_705ec960347a326cbcb5a6c0ff8f7767_Traceguids
0x180018ff3  mov     rcx, cs:WPP_GLOBAL_Control
0x180018ffa  mov     rcx, [rcx+10h]
0x180018ffe  call    WPP_SF_s
0x180019003  mov     ebx, 80004005h
0x180019008  mov     [rsp+68h+var_48], ebx
0x18001900c  test    rsi, rsi
0x18001900f  jz      short loc_180019020
0x180019011  mov     rax, [rsi]
0x180019014  mov     rcx, rsi
0x180019017  mov     rax, [rax+10h]
0x18001901b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019020  mov     rcx, [rsp+68h+arg_0]
0x180019025  test    rcx, rcx
0x180019028  jz      short loc_180019036
0x18001902a  mov     rax, [rcx]
0x18001902d  mov     rax, [rax+10h]
0x180019031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019036  mov     rcx, [rsp+68h+arg_10]
0x18001903e  test    rcx, rcx
0x180019041  jz      short loc_18001904F
0x180019043  mov     rax, [rcx]
0x180019046  mov     rax, [rax+10h]
0x18001904a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001904f  mov     eax, ebx
0x180019051  add     rsp, 30h
0x180019055  pop     r15
0x180019057  pop     r14
0x180019059  pop     r13
0x18001905b  pop     r12
0x18001905d  pop     rdi
0x18001905e  pop     rsi
0x18001905f  pop     rbx
0x180019060  retn
0x18002efe9  push    rbp
0x18002efeb  sub     rsp, 20h
0x18002efef  mov     rbp, rdx
0x18002eff2  mov     rcx, [rbp+88h]
0x18002eff9  test    rcx, rcx
0x18002effc  jz      short loc_18002F00B
0x18002effe  mov     rax, [rcx]
0x18002f001  mov     rax, [rax+10h]
0x18002f005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f00a  nop
0x18002f00b  mov     rcx, [rbp+70h]
0x18002f00f  test    rcx, rcx
0x18002f012  jz      short loc_18002F021
0x18002f014  mov     rax, [rcx]
0x18002f017  mov     rax, [rax+10h]
0x18002f01b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f020  nop
0x18002f021  mov     rcx, [rbp+80h]
0x18002f028  test    rcx, rcx
0x18002f02b  jz      short loc_18002F03A
0x18002f02d  mov     rax, [rcx]
0x18002f030  mov     rax, [rax+10h]
0x18002f034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f039  nop
0x18002f03a  add     rsp, 20h
0x18002f03e  pop     rbp
0x18002f03f  retn
```
