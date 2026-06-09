# CreateStandardPaperSizes(publicdm::CPrintCapsInfo &,NCoreLibrary::TAutoPtrCOM<IXMLDOMElement> &)

- ea: `0x18000be14`
- end: `0x18000c0f4`
- name: `?CreateStandardPaperSizes@@YAJAEAVCPrintCapsInfo@publicdm@@AEAV?$TAutoPtrCOM@UIXMLDOMElement@@@NCoreLibrary@@@Z`
- size: `736`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f720`

## callees

- `0x180004acc`
- `0x1800056e0`
- `0x18000be14`
- `0x18000c0fc`
- `0x18000c224`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000c01c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c01c`

## pseudocode

```c
__int64 __fastcall CreateStandardPaperSizes(__int64 *a1, struct IXMLDOMElement **a2)
{
  __int64 v2; // rax
  __int64 v4; // rax
  int v5; // r15d
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rsi
  __int64 (__fastcall *v9)(__int64); // rdi
  unsigned int v10; // ebx
  unsigned int v11; // eax
  __int64 v12; // rcx
  unsigned int v13; // ebx
  __int64 v14; // rcx
  __int64 v15; // rsi
  __int64 (__fastcall *v16)(__int64); // rdi
  unsigned int v17; // ebx
  unsigned int v18; // eax
  unsigned int v19; // edi
  unsigned int i; // esi
  __int64 v21; // rax
  OLECHAR *v22; // rbx
  int v23; // r12d
  const OLECHAR *v24; // r13
  __int64 v25; // r8
  struct publicdm::PaperSizeEntry **v26; // r9
  BSTR v27; // rax
  int v28; // eax
  __int64 v30; // [rsp+20h] [rbp-38h] BYREF
  __int128 v31; // [rsp+28h] [rbp-30h] BYREF
  __int64 v32; // [rsp+38h] [rbp-20h] BYREF
  __int64 v33; // [rsp+40h] [rbp-18h]
  __int16 v34; // [rsp+48h] [rbp-10h]
  int v35; // [rsp+A0h] [rbp+48h]
  __int64 v37; // [rsp+B0h] [rbp+58h] BYREF
  __int64 v38; // [rsp+B8h] [rbp+60h] BYREF

  v2 = *a1;
  v30 = 0;
  v37 = 0;
  v38 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64 *))(v2 + 16))(a1);
  v5 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v4 + 80LL))(v4, a1[2], &v30);
  if ( v5 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64 *))(*a1 + 16))(a1);
    v5 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v6 + 96LL))(v6, a1[2], &v37);
    if ( v5 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64 *))(*a1 + 16))(a1);
      v5 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v7 + 88LL))(v7, a1[2], &v38);
      if ( v5 >= 0 )
      {
        v8 = v37;
        v9 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 40LL);
        v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 40LL))(v38);
        v11 = v9(v8);
        v12 = v37;
        if ( v11 >= v10 )
          v12 = v38;
        v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 40LL))(v12);
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v30 + 40LL))(v30) >= v13 )
        {
          v15 = v37;
          v16 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 40LL);
          v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 40LL))(v38);
          v18 = v16(v15);
          v14 = v37;
          if ( v18 >= v17 )
            v14 = v38;
        }
        else
        {
          v14 = v30;
        }
        v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 40LL))(v14);
        for ( i = 0; i < v19; ++i )
        {
          v21 = *a1;
          v32 = 0;
          v31 = 0;
          v33 = 0;
          v22 = (OLECHAR *)(*(__int64 (__fastcall **)(__int64 *))(v21 + 8))(a1);
          v35 = *(_DWORD *)((*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v37 + 56LL))(v37, i) + 4);
          v23 = 100 * *(_DWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v37 + 56LL))(v37, i);
          v24 = (const OLECHAR *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v38 + 56LL))(v38, i);
          v34 = *(_WORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v30 + 56LL))(v30, i);
          if ( (int)PaperSizeOption::SetPrintTicketMappingFromID((PaperSizeOption *)&v31, v22, v25, v26) >= 0 && v24 )
          {
            v27 = SysAllocString(v24);
            NCoreLibrary::TAutoPtrBSTR::operator=(&v32, v27);
          }
          if ( v23 && (v28 = 100 * v35) != 0 )
          {
            LODWORD(v33) = v23;
            HIDWORD(v33) = 100 * v35;
          }
          else
          {
            v28 = HIDWORD(v33);
            v23 = v33;
          }
          if ( (_QWORD)v31 && *((_QWORD *)&v31 + 1) || v23 && v28 )
            v5 = PaperSizeOption::WriteToPrintTicket((__int64)&v31, (NPrintTicketUtil::CPrintTicketWrapper *)a1[14], a2);
          NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v32);
          NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset((char *)&v31 + 8);
          NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v31);
        }
      }
    }
  }
  if ( v38 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    v38 = 0;
  }
  if ( v37 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
  }
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000be14  mov     [rsp-40h+arg_8], rdx
0x18000be19  push    rbp
0x18000be1a  push    rbx
0x18000be1b  push    rsi
0x18000be1c  push    rdi
0x18000be1d  push    r12
0x18000be1f  push    r13
0x18000be21  push    r14
0x18000be23  push    r15
0x18000be25  mov     rbp, rsp
0x18000be28  sub     rsp, 58h
0x18000be2c  mov     rax, [rcx]
0x18000be2f  xor     ebx, ebx
0x18000be31  mov     r14, rcx
0x18000be34  mov     [rbp+var_38], rbx
0x18000be38  mov     [rbp+arg_10], rbx
0x18000be3c  mov     [rbp+arg_18], rbx
0x18000be40  mov     rax, [rax+10h]
0x18000be44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be49  mov     rdx, [r14+10h]
0x18000be4d  lea     r8, [rbp+var_38]
0x18000be51  mov     r9, rax
0x18000be54  mov     rcx, [rax]
0x18000be57  mov     rax, [rcx+50h]
0x18000be5b  mov     rcx, r9
0x18000be5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be63  mov     r15d, eax
0x18000be66  test    eax, eax
0x18000be68  js      loc_18000C099
0x18000be6e  mov     rax, [r14]
0x18000be71  mov     rcx, r14
0x18000be74  mov     rax, [rax+10h]
0x18000be78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be7d  mov     rdx, [r14+10h]
0x18000be81  lea     r8, [rbp+arg_10]
0x18000be85  mov     r9, rax
0x18000be88  mov     rcx, [rax]
0x18000be8b  mov     rax, [rcx+60h]
0x18000be8f  mov     rcx, r9
0x18000be92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be97  mov     r15d, eax
0x18000be9a  test    eax, eax
0x18000be9c  js      loc_18000C099
0x18000bea2  mov     rax, [r14]
0x18000bea5  mov     rcx, r14
0x18000bea8  mov     rax, [rax+10h]
0x18000beac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000beb1  mov     rdx, [r14+10h]
0x18000beb5  lea     r8, [rbp+arg_18]
0x18000beb9  mov     r9, rax
0x18000bebc  mov     rcx, [rax]
0x18000bebf  mov     rax, [rcx+58h]
0x18000bec3  mov     rcx, r9
0x18000bec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000becb  mov     r15d, eax
0x18000bece  test    eax, eax
0x18000bed0  js      loc_18000C099
0x18000bed6  mov     rsi, [rbp+arg_10]
0x18000beda  mov     rcx, [rbp+arg_18]
0x18000bede  mov     rax, [rsi]
0x18000bee1  mov     rdx, [rcx]
0x18000bee4  mov     rdi, [rax+28h]
0x18000bee8  mov     rax, [rdx+28h]
0x18000beec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bef1  mov     ebx, eax
0x18000bef3  mov     rcx, rsi
0x18000bef6  mov     rax, rdi
0x18000bef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000befe  mov     rcx, [rbp+arg_10]
0x18000bf02  cmp     eax, ebx
0x18000bf04  jb      short loc_18000BF0A
0x18000bf06  mov     rcx, [rbp+arg_18]
0x18000bf0a  mov     rax, [rcx]
0x18000bf0d  mov     rax, [rax+28h]
0x18000bf11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf16  mov     rcx, [rbp+var_38]
0x18000bf1a  mov     ebx, eax
0x18000bf1c  mov     rax, [rcx]
0x18000bf1f  mov     rax, [rax+28h]
0x18000bf23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf28  cmp     eax, ebx
0x18000bf2a  jnb     short loc_18000BF32
0x18000bf2c  mov     rcx, [rbp+var_38]
0x18000bf30  jmp     short loc_18000BF66
0x18000bf32  mov     rsi, [rbp+arg_10]
0x18000bf36  mov     rcx, [rbp+arg_18]
0x18000bf3a  mov     rax, [rsi]
0x18000bf3d  mov     rdx, [rcx]
0x18000bf40  mov     rdi, [rax+28h]
0x18000bf44  mov     rax, [rdx+28h]
0x18000bf48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf4d  mov     ebx, eax
0x18000bf4f  mov     rcx, rsi
0x18000bf52  mov     rax, rdi
0x18000bf55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf5a  mov     rcx, [rbp+arg_10]
0x18000bf5e  cmp     eax, ebx
0x18000bf60  jb      short loc_18000BF66
0x18000bf62  mov     rcx, [rbp+arg_18]
0x18000bf66  mov     rax, [rcx]
0x18000bf69  mov     rax, [rax+28h]
0x18000bf6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf72  xor     ebx, ebx
0x18000bf74  mov     edi, eax
0x18000bf76  mov     esi, ebx
0x18000bf78  test    eax, eax
0x18000bf7a  jz      loc_18000C099
0x18000bf80  mov     rax, [r14]
0x18000bf83  xorps   xmm0, xmm0
0x18000bf86  mov     rcx, r14
0x18000bf89  mov     [rbp+var_20], rbx
0x18000bf8d  movdqu  [rbp+var_30], xmm0
0x18000bf92  mov     [rbp+var_18], 0
0x18000bf9a  mov     rax, [rax+8]
0x18000bf9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfa3  mov     rcx, [rbp+arg_10]
0x18000bfa7  mov     rbx, rax
0x18000bfaa  mov     rdx, [rcx]
0x18000bfad  mov     rax, [rdx+38h]
0x18000bfb1  mov     edx, esi
0x18000bfb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfb8  mov     rcx, [rbp+arg_10]
0x18000bfbc  mov     eax, [rax+4]
0x18000bfbf  mov     rdx, [rcx]
0x18000bfc2  mov     [rbp+arg_0], eax
0x18000bfc5  mov     rax, [rdx+38h]
0x18000bfc9  mov     edx, esi
0x18000bfcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfd0  mov     rcx, [rbp+arg_18]
0x18000bfd4  mov     edx, esi
0x18000bfd6  imul    r12d, [rax], 64h ; 'd'
0x18000bfda  mov     rax, [rcx]
0x18000bfdd  mov     rax, [rax+38h]
0x18000bfe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfe6  mov     rcx, [rbp+var_38]
0x18000bfea  mov     r13, rax
0x18000bfed  mov     rdx, [rcx]
0x18000bff0  mov     rax, [rdx+38h]
0x18000bff4  mov     edx, esi
0x18000bff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bffb  mov     rdx, rbx; psz
0x18000bffe  movzx   ecx, word ptr [rax]
0x18000c001  mov     [rbp+var_10], cx
0x18000c005  lea     rcx, [rbp+var_30]; this
0x18000c009  call    ?SetPrintTicketMappingFromID@PaperSizeOption@@AEAAJPEBG@Z; PaperSizeOption::SetPrintTicketMappingFromID(ushort const *)
0x18000c00e  xor     ebx, ebx
0x18000c010  test    eax, eax
0x18000c012  js      short loc_18000C02E
0x18000c014  test    r13, r13
0x18000c017  jz      short loc_18000C02E
0x18000c019  mov     rcx, r13; psz
0x18000c01c  call    cs:__imp_SysAllocString
0x18000c022  mov     rdx, rax
0x18000c025  lea     rcx, [rbp+var_20]
0x18000c029  call    ??4TAutoPtrBSTR@NCoreLibrary@@QEAAPEAGPEAG@Z; NCoreLibrary::TAutoPtrBSTR::operator=(ushort *)
0x18000c02e  test    r12d, r12d
0x18000c031  jz      short loc_18000C044
0x18000c033  imul    eax, [rbp+arg_0], 64h ; 'd'
0x18000c037  test    eax, eax
0x18000c039  jz      short loc_18000C044
0x18000c03b  mov     dword ptr [rbp+var_18], r12d
0x18000c03f  mov     dword ptr [rbp+var_18+4], eax
0x18000c042  jmp     short loc_18000C04B
0x18000c044  mov     eax, dword ptr [rbp+var_18+4]
0x18000c047  mov     r12d, dword ptr [rbp+var_18]
0x18000c04b  cmp     qword ptr [rbp+var_30], rbx
0x18000c04f  jz      short loc_18000C057
0x18000c051  cmp     qword ptr [rbp+var_30+8], rbx
0x18000c055  jnz     short loc_18000C060
0x18000c057  test    r12d, r12d
0x18000c05a  jz      short loc_18000C074
0x18000c05c  test    eax, eax
0x18000c05e  jz      short loc_18000C074
0x18000c060  mov     r8, [rbp+arg_8]
0x18000c064  lea     rcx, [rbp+var_30]
0x18000c068  mov     rdx, [r14+70h]
0x18000c06c  call    ?WriteToPrintTicket@PaperSizeOption@@QEAAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@AEAV?$TAutoPtrCOM@UIXMLDOMElement@@@NCoreLibrary@@@Z; PaperSizeOption::WriteToPrintTicket(NPrintTicketUtil::CPrintTicketWrapper *,NCoreLibrary::TAutoPtrCOM<IXMLDOMElement> &)
0x18000c071  mov     r15d, eax
0x18000c074  lea     rcx, [rbp+var_20]
0x18000c078  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18000c07d  lea     rcx, [rbp+var_30+8]
0x18000c081  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18000c086  lea     rcx, [rbp+var_30]
0x18000c08a  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18000c08f  inc     esi
0x18000c091  cmp     esi, edi
0x18000c093  jb      loc_18000BF80
0x18000c099  mov     rcx, [rbp+arg_18]
0x18000c09d  test    rcx, rcx
0x18000c0a0  jz      short loc_18000C0B2
0x18000c0a2  mov     rax, [rcx]
0x18000c0a5  mov     rax, [rax+10h]
0x18000c0a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0ae  mov     [rbp+arg_18], rbx
0x18000c0b2  mov     rcx, [rbp+arg_10]
0x18000c0b6  test    rcx, rcx
0x18000c0b9  jz      short loc_18000C0CB
0x18000c0bb  mov     rax, [rcx]
0x18000c0be  mov     rax, [rax+10h]
0x18000c0c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0c7  mov     [rbp+arg_10], rbx
0x18000c0cb  mov     rcx, [rbp+var_38]
0x18000c0cf  test    rcx, rcx
0x18000c0d2  jz      short loc_18000C0E0
0x18000c0d4  mov     rax, [rcx]
0x18000c0d7  mov     rax, [rax+10h]
0x18000c0db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0e0  mov     eax, r15d
0x18000c0e3  add     rsp, 58h
0x18000c0e7  pop     r15
0x18000c0e9  pop     r14
0x18000c0eb  pop     r13
0x18000c0ed  pop     r12
0x18000c0ef  pop     rdi
0x18000c0f0  pop     rsi
0x18000c0f1  pop     rbx
0x18000c0f2  pop     rbp
0x18000c0f3  retn
```
