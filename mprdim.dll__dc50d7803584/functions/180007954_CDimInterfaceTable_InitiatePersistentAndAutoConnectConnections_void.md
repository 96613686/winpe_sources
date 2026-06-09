# CDimInterfaceTable::InitiatePersistentAndAutoConnectConnections(void)

- ea: `0x180007954`
- end: `0x180007bea`
- name: `?InitiatePersistentAndAutoConnectConnections@CDimInterfaceTable@@QEAAXXZ`
- size: `662`
- prototype: `void __fastcall(CDimInterfaceTable *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180011eb0`

## callees

- `0x180005550`
- `0x180006ce0`
- `0x180007954`
- `0x18000df70`
- `0x18001e4d4`
- `0x1800219f4`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `MPRDDM!TimerQInsert` at `0x180007abe`
- `MPRDDM!TimerQInsert` at `0x180007abe`
- `MPRDDM!ReConnectPersistentInterface` at `0x180007a8f`
- `MPRDDM!ReConnectPersistentInterface` at `0x180007aaf`
- `MPRDDM!TimerQRemove` at `0x180007a99`
- `MPRDDM!TimerQRemove` at `0x180007a99`
- `MPRDDM!IfObjectSetDialoutHoursRestriction` at `0x180007b73`
- `MPRDDM!IfObjectSetDialoutHoursRestriction` at `0x180007b73`
- `MPRDDM!RasConnectionInitiate` at `0x180007a58`
- `MPRDDM!RasConnectionInitiate` at `0x180007a58`

## pseudocode

```c
void __fastcall CDimInterfaceTable::InitiatePersistentAndAutoConnectConnections(CDimInterfaceTable *this)
{
  CDimInterfaceTable *v1; // r14
  _QWORD *v2; // rdi
  _QWORD *v3; // rbx
  unsigned int v4; // esi
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rcx
  __int128 *v10; // r9
  bool v11; // zf
  int v12; // ecx
  __int64 v13; // rax
  __int64 v14; // rcx
  _QWORD *i; // rax
  __int128 v16; // [rsp+30h] [rbp-D0h] BYREF
  int v17; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v18; // [rsp+44h] [rbp-BCh]
  __int128 v19; // [rsp+54h] [rbp-ACh]
  int v20; // [rsp+64h] [rbp-9Ch]
  int v21; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v22[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v1 = g_pCDimInterfaceTable;
  v21 = 0;
  v16 = 0;
  memset_0(v22, 0, sizeof(v22));
  v17 = 0;
  v18 = 0;
  v20 = 0;
  v19 = 0;
  CDimInterfaceTable::AcquireShared(v1);
  v2 = (_QWORD *)*((_QWORD *)v1 + 28);
  v3 = (_QWORD *)*v2;
  while ( v3 != v2 )
  {
    if ( CDimInterface::IsDimFullRouterInterface((CDimInterface *)v3[4]) )
    {
      (**(void (__fastcall ***)(_QWORD))v3[4])(v3[4]);
      if ( ((*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v3[4] + 104LL))(v3[4]) & 2) == 0
        && ((*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v3[4] + 104LL))(v3[4]) & 0x8000) == 0
        || (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v3[4] + 56LL))(v3[4])
        || (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)v3[4] + 40LL))(v3[4]) )
      {
        v13 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v3[4] + 16LL))(v3[4]);
        IfObjectSetDialoutHoursRestriction(v13);
      }
      else
      {
        v4 = RasConnectionInitiate(v3[4], 0);
        if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)v3[4] + 456LL))(v3[4]) == 9 && v4 )
        {
          v5 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v3[4] + 16LL))(v3[4]);
          TimerQRemove(v5, ReConnectPersistentInterface);
          v6 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v3[4] + 16LL))(v3[4]);
          TimerQInsert(v6, 30, ReConnectPersistentInterface);
        }
        if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
        {
          LOWORD(v21) = 0;
          LOWORD(v17) = 0;
          v7 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v3[4] + 280LL))(v3[4]);
          FormatRRASErrorString(&v21, L"Initiated persistent connection to %ws, dwError %d", v7, v4);
          if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
          {
            v8 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v3[4] + 280LL))(v3[4]);
            v9 = v3[4];
            v10 = &v16;
            v11 = v9 == -3104;
            v12 = v9 + 3104;
            if ( !v11 )
              LODWORD(v10) = v12;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDimParamTraceInfo,
              (unsigned int)&v21,
              (_DWORD)v10,
              v8,
              (__int64)&v17);
          }
        }
      }
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v3[4] + 8LL))(v3[4]);
    }
    if ( !*((_BYTE *)v3 + 49) )
    {
      v14 = v3[2];
      if ( *(_BYTE *)(v14 + 49) )
      {
        for ( i = (_QWORD *)v3[1]; !*((_BYTE *)i + 49) && v3 == (_QWORD *)i[2]; i = (_QWORD *)i[1] )
          v3 = i;
      }
      else
      {
        i = std::_Tree_val<std::_Tmap_traits<void *,std::tr1::shared_ptr<CDimInterface>,std::less<void *>,std::allocator<std::pair<void * const,std::tr1::shared_ptr<CDimInterface>>>,0>>::_Min((_QWORD *)v14);
      }
      v3 = i;
    }
  }
  CDimInterfaceTable::ReleaseShared(v1);
}

```

## disassembly

```asm
0x180007954  push    rbp
0x180007956  push    rbx
0x180007957  push    rsi
0x180007958  push    rdi
0x180007959  push    r14
0x18000795b  lea     rbp, [rsp-780h]
0x180007963  sub     rsp, 880h
0x18000796a  mov     rax, cs:__security_cookie
0x180007971  xor     rax, rsp
0x180007974  mov     [rbp+7A0h+var_30], rax
0x18000797b  mov     r14, cs:?g_pCDimInterfaceTable@@3PEAVCDimInterfaceTable@@EA; CDimInterfaceTable * g_pCDimInterfaceTable
0x180007982  lea     rcx, [rsp+8A0h+var_82C]; void *
0x180007987  xorps   xmm0, xmm0
0x18000798a  xor     eax, eax
0x18000798c  xor     edx, edx; Val
0x18000798e  mov     [rsp+8A0h+var_830], eax
0x180007992  mov     r8d, 7FCh; Size
0x180007998  movups  [rsp+8A0h+var_870], xmm0
0x18000799d  call    memset_0
0x1800079a2  xor     eax, eax
0x1800079a4  xorps   xmm0, xmm0
0x1800079a7  mov     rcx, r14; this
0x1800079aa  mov     [rsp+8A0h+var_860], eax
0x1800079ae  movups  [rsp+8A0h+var_85C], xmm0
0x1800079b3  mov     [rsp+8A0h+var_83C], eax
0x1800079b7  movups  [rsp+8A0h+var_84C], xmm0
0x1800079bc  call    ?AcquireShared@CDimInterfaceTable@@UEAAXXZ; CDimInterfaceTable::AcquireShared(void)
0x1800079c1  mov     rdi, [r14+0E0h]
0x1800079c8  mov     rbx, [rdi]
0x1800079cb  cmp     rbx, rdi
0x1800079ce  jz      loc_180007BC5
0x1800079d4  mov     rcx, [rbx+20h]; this
0x1800079d8  call    ?IsDimFullRouterInterface@CDimInterface@@QEBA_NXZ; CDimInterface::IsDimFullRouterInterface(void)
0x1800079dd  test    al, al
0x1800079df  jz      loc_180007B89
0x1800079e5  mov     rcx, [rbx+20h]
0x1800079e9  mov     rax, [rcx]
0x1800079ec  mov     rax, [rax]
0x1800079ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079f4  mov     rcx, [rbx+20h]
0x1800079f8  mov     rax, [rcx]
0x1800079fb  mov     rax, [rax+68h]
0x1800079ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a04  test    al, 2
0x180007a06  jnz     short loc_180007A22
0x180007a08  mov     rcx, [rbx+20h]
0x180007a0c  mov     rax, [rcx]
0x180007a0f  mov     rax, [rax+68h]
0x180007a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a18  bt      eax, 0Fh
0x180007a1c  jnb     loc_180007B60
0x180007a22  mov     rcx, [rbx+20h]
0x180007a26  mov     rax, [rcx]
0x180007a29  mov     rax, [rax+38h]
0x180007a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a32  test    al, al
0x180007a34  jnz     loc_180007B60
0x180007a3a  mov     rcx, [rbx+20h]
0x180007a3e  mov     rax, [rcx]
0x180007a41  mov     rax, [rax+28h]
0x180007a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a4a  test    eax, eax
0x180007a4c  jnz     loc_180007B60
0x180007a52  mov     rcx, [rbx+20h]
0x180007a56  xor     edx, edx
0x180007a58  call    cs:__imp_RasConnectionInitiate
0x180007a5e  mov     rdx, [rbx+20h]
0x180007a62  mov     esi, eax
0x180007a64  mov     rcx, [rdx]
0x180007a67  mov     rax, [rcx+1C8h]
0x180007a6e  mov     rcx, rdx
0x180007a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a76  cmp     eax, 9
0x180007a79  jnz     short loc_180007AC4
0x180007a7b  test    esi, esi
0x180007a7d  jz      short loc_180007AC4
0x180007a7f  mov     rcx, [rbx+20h]
0x180007a83  mov     rax, [rcx]
0x180007a86  mov     rax, [rax+10h]
0x180007a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a8f  mov     rdx, cs:__imp_ReConnectPersistentInterface
0x180007a96  mov     rcx, rax
0x180007a99  call    cs:__imp_TimerQRemove
0x180007a9f  mov     rcx, [rbx+20h]
0x180007aa3  mov     rax, [rcx]
0x180007aa6  mov     rax, [rax+10h]
0x180007aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aaf  mov     r8, cs:__imp_ReConnectPersistentInterface
0x180007ab6  mov     rcx, rax
0x180007ab9  mov     edx, 1Eh
0x180007abe  call    cs:__imp_TimerQInsert
0x180007ac4  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x180007acb  jz      loc_180007B79
0x180007ad1  xor     eax, eax
0x180007ad3  mov     word ptr [rsp+8A0h+var_830], ax
0x180007ad8  mov     word ptr [rsp+8A0h+var_860], ax
0x180007add  mov     rcx, [rbx+20h]
0x180007ae1  mov     rax, [rcx]
0x180007ae4  mov     rax, [rax+118h]
0x180007aeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007af0  mov     r8, rax
0x180007af3  lea     rdx, aInitiatedPersi; "Initiated persistent connection to %ws,"...
0x180007afa  mov     r9d, esi
0x180007afd  lea     rcx, [rsp+8A0h+var_830]
0x180007b02  call    FormatRRASErrorString
0x180007b07  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x180007b0e  jz      short loc_180007B79
0x180007b10  mov     rcx, [rbx+20h]
0x180007b14  mov     rax, [rcx]
0x180007b17  mov     rax, [rax+118h]
0x180007b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b23  mov     rcx, [rbx+20h]
0x180007b27  lea     r9, [rsp+8A0h+var_870]
0x180007b2c  add     rcx, 0C20h
0x180007b33  lea     r8, [rsp+8A0h+var_830]
0x180007b38  lea     rdx, RasDimParamTraceInfo
0x180007b3f  cmovnz  r9, rcx
0x180007b43  lea     rcx, [rsp+8A0h+var_860]
0x180007b48  mov     [rsp+8A0h+var_878], rcx
0x180007b4d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007b54  mov     [rsp+8A0h+var_880], rax
0x180007b59  call    McTemplateU0zjzz_EventWriteTransfer
0x180007b5e  jmp     short loc_180007B79
0x180007b60  mov     rcx, [rbx+20h]
0x180007b64  mov     rax, [rcx]
0x180007b67  mov     rax, [rax+10h]
0x180007b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b70  mov     rcx, rax
0x180007b73  call    cs:__imp_IfObjectSetDialoutHoursRestriction
0x180007b79  mov     rcx, [rbx+20h]
0x180007b7d  mov     rax, [rcx]
0x180007b80  mov     rax, [rax+8]
0x180007b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b89  cmp     byte ptr [rbx+31h], 0
0x180007b8d  jnz     loc_1800079CB
0x180007b93  mov     rcx, [rbx+10h]
0x180007b97  cmp     byte ptr [rcx+31h], 0
0x180007b9b  jnz     short loc_180007BA4
0x180007b9d  call    ?_Min@?$_Tree_val@V?$_Tmap_traits@PEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@U?$less@PEAX@3@V?$allocator@U?$pair@QEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@@std@@@3@$0A@@std@@@std@@SAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@PEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@U?$less@PEAX@3@V?$allocator@U?$pair@QEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@@std@@@3@$0A@@std@@@2@PEAU342@@Z; std::_Tree_val<std::_Tmap_traits<void *,std::tr1::shared_ptr<CDimInterface>,std::less<void *>,std::allocator<std::pair<void * const,std::tr1::shared_ptr<CDimInterface>>>,0>>::_Min(std::_Tree_nod<std::_Tmap_traits<void *,std::tr1::shared_ptr<CDimInterface>,std::less<void *>,std::allocator<std::pair<void * const,std::tr1::shared_ptr<CDimInterface>>>,0>>::_Node *)
0x180007ba2  jmp     short loc_180007BBD
0x180007ba4  mov     rax, [rbx+8]
0x180007ba8  jmp     short loc_180007BB7
0x180007baa  cmp     rbx, [rax+10h]
0x180007bae  jnz     short loc_180007BBD
0x180007bb0  mov     rbx, rax
0x180007bb3  mov     rax, [rax+8]
0x180007bb7  cmp     byte ptr [rax+31h], 0
0x180007bbb  jz      short loc_180007BAA
0x180007bbd  mov     rbx, rax
0x180007bc0  jmp     loc_1800079CB
0x180007bc5  mov     rcx, r14; this
0x180007bc8  call    ?ReleaseShared@CDimInterfaceTable@@UEAAXXZ; CDimInterfaceTable::ReleaseShared(void)
0x180007bcd  mov     rcx, [rbp+7A0h+var_30]
0x180007bd4  xor     rcx, rsp; StackCookie
0x180007bd7  call    __security_check_cookie
0x180007bdc  add     rsp, 880h
0x180007be3  pop     r14
0x180007be5  pop     rdi
0x180007be6  pop     rsi
0x180007be7  pop     rbx
0x180007be8  pop     rbp
0x180007be9  retn
```
