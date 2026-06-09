# CTxtSelection::ReplaceRange(long,ushort const *,IUndoBuilder *,SELRR,long *,ulong)

- ea: `0x180040500`
- end: `0x18004088e`
- name: `?ReplaceRange@CTxtSelection@@UEAAJJPEBGPEAVIUndoBuilder@@W4SELRR@@PEAJK@Z`
- size: `910`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `installer_update`

## callees

- `0x18000c840`
- `0x18000fe40`
- `0x180010260`
- `0x180016470`
- `0x180016d90`
- `0x18001f4a0`
- `0x180022ad4`
- `0x180039afc`
- `0x18003a2f0`
- `0x18003ed40`
- `0x180040500`
- `0x180041cf8`
- `0x180043e88`
- `0x180045000`
- `0x180045230`
- `0x18004a284`
- `0x18004a340`
- `0x180075420`
- `0x1800820e0`
- `0x1800831f8`
- `0x180095010`

## pseudocode

```c
__int64 __fastcall CTxtSelection::ReplaceRange(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int a7)
{
  const unsigned __int16 *v9; // r8
  CTxtPtr *v10; // r11
  int v11; // edx
  int v12; // ecx
  unsigned int v14; // ebp
  CTxtPtr *v15; // r11
  int v16; // eax
  int v17; // ecx
  unsigned int v18; // r12d
  unsigned int v19; // r15d
  bool v20; // sf
  int v21; // eax
  int v22; // edx
  __int64 v23; // rax
  unsigned int v24; // edi
  int v25; // r13d
  int v26; // r14d
  unsigned int v27; // ebp
  __int64 v28; // r8
  __int64 v29; // r9
  int v30; // edx
  int v31; // ecx
  __int64 v32; // rax
  __int64 v33; // rcx
  int v34; // eax
  _BYTE v35[32]; // [rsp+40h] [rbp-78h] BYREF
  __int16 v36; // [rsp+60h] [rbp-58h]
  int TextLength; // [rsp+C8h] [rbp+10h]

  TextLength = CTxtPtr::GetTextLength((CTxtPtr *)(a1 + 24));
  *(_DWORD *)(a1 + 140) = 0;
  if ( v11 < 0 )
    a2 = CW32System::wcslen(v9);
  v12 = *(_DWORD *)(a1 + 88);
  if ( !v12 && !a2 )
    return 0;
  v14 = *(_DWORD *)(a1 + 136);
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 48) + 180LL) & 0x10000) == 0
    && (!v12
     && *v9 != 13
     && CTxtPtr::GetChar(v10) == 13
     && CTxtPtr::GetPrevChar(v15) == 9
     && (*((_WORD *)CTxtSelection::GetPF((CTxtSelection *)a1) + 1) & 0x4000) != 0
     || *(_DWORD *)(a1 + 88) != TextLength
     && ((*(_WORD *)(*(_QWORD *)(a1 + 48) + 184LL) & 0x2000) != 0
      && (*((_WORD *)CRchTxtPtr::GetPF((CRchTxtPtr *)(a1 + 8)) + 1) & 0x100) != 0
      || (unsigned int)CRchTxtPtr::IsHidden((CRchTxtPtr *)(a1 + 8)) && (a7 & 0x10) == 0)) )
  {
    CTxtEdit::Beep(*(CTxtEdit **)(a1 + 48));
    return 0;
  }
  CCallMgr::SetSelectionChanged(*(CCallMgr **)(*(_QWORD *)(a1 + 48) + 144LL));
  CTxtSelection::CheckTableSelection((CTxtSelection *)a1);
  v16 = *(_DWORD *)(a1 + 88);
  v17 = *(_DWORD *)(a1 + 112);
  v18 = *(_DWORD *)(a1 + 40);
  v19 = v18 - v16;
  v20 = v16 < 0;
  v21 = v17;
  if ( v20 )
  {
    v18 = v19;
    v19 = *(_DWORD *)(a1 + 40);
  }
  v22 = v17 + *(_DWORD *)(a1 + 116);
  if ( v17 >= v22 )
    v21 = v17 + *(_DWORD *)(a1 + 116);
  if ( (int)v19 > v21 )
    goto LABEL_26;
  if ( v17 <= v22 )
    v17 += *(_DWORD *)(a1 + 116);
  if ( (int)v18 < v17 )
  {
LABEL_26:
    CTxtSelection::ShowSelection((CTxtSelection *)a1, 0);
    *(_DWORD *)(a1 + 136) |= 8u;
  }
  v23 = *(_QWORD *)(a1 + 48);
  *(_DWORD *)(a1 + 136) &= 0xFFFFFFEE;
  if ( (*(_DWORD *)(v23 + 180) & 0x10000) != 0
    || (*(unsigned int (__fastcall **)(_QWORD, _QWORD, __int64))(**(_QWORD **)(a1 + 104) + 264LL))(
         *(_QWORD *)(a1 + 104),
         v19,
         0xFFFFFFFFLL) )
  {
    v25 = 0;
    v26 = 0;
    v27 = v14 >> 4;
    if ( a4 )
    {
      if ( a5 == 1 )
      {
        v28 = *(unsigned int *)(a1 + 40);
        v29 = *(unsigned int *)(a1 + 88);
      }
      else
      {
        v29 = 0;
        v28 = v19;
        if ( a5 == 3 )
          v28 = v18;
      }
      HandleSelectionAEInfo(*(_QWORD *)(a1 + 48), a4, v28, v29, v19 + a2, 0, 1);
    }
    v30 = *(_DWORD *)(a1 + 88);
    if ( v30 == TextLength && !a2 )
    {
      v25 = 1;
      CRchTxtPtr::Advance((CRchTxtPtr *)(a1 + 8), -v30);
      *(_DWORD *)(a1 + 88) = -*(_DWORD *)(a1 + 88);
      if ( (*(_WORD *)(*(_QWORD *)(a1 + 48) + 184LL) & 0x2000) != 0
        && *((__int16 *)CTxtSelection::GetPF((CTxtSelection *)a1) + 16) <= -2
        && *((__int16 *)CTxtSelection::GetPF((CTxtSelection *)a1) + 16) >= -10 )
      {
        v26 = 1;
      }
    }
    v24 = CTxtRange::ReplaceRange(a1, a2, a3, a4, 0, a6, a7);
    *(_DWORD *)(a1 + 112) = *(_DWORD *)(a1 + 40);
    v31 = *(_DWORD *)(a1 + 136);
    *(_DWORD *)(a1 + 116) = 0;
    *(_DWORD *)(a1 + 136) = v31 ^ ((unsigned __int8)v31 ^ (unsigned __int8)(16 * v27)) & 0x10;
    if ( v24 == a2 )
    {
      if ( v25 )
      {
        v36 = -2;
        if ( !v26 )
          v36 = -1;
        CTxtRange::SetParaStyle((CTxtRange *)a1, (const struct CParaFormat *)v35, 0, 0x400u);
        v32 = *(_QWORD *)(a1 + 48);
        if ( (*(_BYTE *)(v32 + 192) & 1) != 0 )
        {
          if ( *(char *)(v32 + 180) < 0 && (*(_WORD *)(v32 + 184) & 0x4000) == 0 )
          {
            CTxtSelection::MatchKeyboardToPara((CTxtSelection *)a1);
            CTxtSelection::CheckSynchCharSet((CTxtSelection *)a1, 0);
          }
        }
        else
        {
          CTxtRange::Update_iFormat((CTxtRange *)a1, -1);
        }
      }
      v33 = *(_QWORD *)(a1 + 48);
      v34 = *(_DWORD *)(v33 + 180);
      if ( (v34 & 8) != 0 )
        CTxtSelection::UpdateCaret((CTxtSelection *)a1, v27 & 1, 0);
      else
        *(_DWORD *)(v33 + 180) = v34 | 0x8000;
    }
  }
  else
  {
    return 0;
  }
  return v24;
}

```

## disassembly

```asm
0x180040500  mov     [rsp+arg_0], rbx
0x180040505  mov     [rsp+arg_18], r9
0x18004050a  mov     [rsp+arg_10], r8
0x18004050f  push    rbp
0x180040510  push    rsi
0x180040511  push    rdi
0x180040512  push    r12
0x180040514  push    r13
0x180040516  push    r14
0x180040518  push    r15
0x18004051a  sub     rsp, 80h
0x180040521  lea     r11, [rcx+18h]
0x180040525  mov     rbx, rcx
0x180040528  mov     rcx, r11; this
0x18004052b  mov     esi, edx
0x18004052d  call    ?GetTextLength@CTxtPtr@@QEBAJXZ; CTxtPtr::GetTextLength(void)
0x180040532  mov     [rsp+0B8h+arg_8], eax
0x180040539  mov     r14d, eax
0x18004053c  mov     dword ptr [rbx+8Ch], 0
0x180040546  test    edx, edx
0x180040548  jns     short loc_180040555
0x18004054a  mov     rcx, r8; unsigned __int16 *
0x18004054d  call    ?wcslen@CW32System@@SA_KPEBG@Z; CW32System::wcslen(ushort const *)
0x180040552  mov     rsi, rax
0x180040555  mov     ecx, [rbx+58h]
0x180040558  test    ecx, ecx
0x18004055a  jnz     short loc_180040567
0x18004055c  test    esi, esi
0x18004055e  jnz     short loc_180040567
0x180040560  xor     eax, eax
0x180040562  jmp     loc_180040872
0x180040567  mov     ebp, [rbx+88h]
0x18004056d  lea     rdi, [rbx+8]
0x180040571  mov     rax, [rdi+28h]
0x180040575  mov     r13d, 10000h
0x18004057b  mov     edx, 2000h
0x180040580  mov     r15d, 4000h
0x180040586  test    [rax+0B4h], r13d
0x18004058d  jnz     loc_180040618
0x180040593  test    ecx, ecx
0x180040595  jnz     short loc_1800405CE
0x180040597  cmp     word ptr [r8], 0Dh
0x18004059c  jz      short loc_1800405CE
0x18004059e  mov     rcx, r11; this
0x1800405a1  call    ?GetChar@CTxtPtr@@QEAAGXZ; CTxtPtr::GetChar(void)
0x1800405a6  cmp     ax, 0Dh
0x1800405aa  jnz     short loc_1800405C9
0x1800405ac  mov     rcx, r11; this
0x1800405af  call    ?GetPrevChar@CTxtPtr@@QEAAGXZ; CTxtPtr::GetPrevChar(void)
0x1800405b4  cmp     ax, 9
0x1800405b8  jnz     short loc_1800405C9
0x1800405ba  mov     rcx, rbx; this
0x1800405bd  call    ?GetPF@CTxtSelection@@QEAAPEBVCParaFormat@@XZ; CTxtSelection::GetPF(void)
0x1800405c2  test    [rax+2], r15w
0x1800405c7  jnz     short loc_18004060A
0x1800405c9  mov     edx, 2000h
0x1800405ce  cmp     [rbx+58h], r14d
0x1800405d2  jz      short loc_180040618
0x1800405d4  mov     rax, [rbx+30h]
0x1800405d8  test    [rax+0B8h], dx
0x1800405df  jz      short loc_1800405F4
0x1800405e1  mov     rcx, rdi; this
0x1800405e4  call    ?GetPF@CRchTxtPtr@@QEBAPEBVCParaFormat@@XZ; CRchTxtPtr::GetPF(void)
0x1800405e9  mov     ecx, 100h
0x1800405ee  test    [rax+2], cx
0x1800405f2  jnz     short loc_18004060A
0x1800405f4  mov     rcx, rdi; this
0x1800405f7  call    ?IsHidden@CRchTxtPtr@@QEBAHXZ; CRchTxtPtr::IsHidden(void)
0x1800405fc  test    eax, eax
0x1800405fe  jz      short loc_180040618
0x180040600  test    byte ptr [rsp+0B8h+arg_30], 10h
0x180040608  jnz     short loc_180040618
0x18004060a  mov     rcx, [rbx+30h]; this
0x18004060e  call    ?Beep@CTxtEdit@@QEAAXXZ; CTxtEdit::Beep(void)
0x180040613  jmp     loc_180040560
0x180040618  mov     rcx, [rbx+30h]
0x18004061c  mov     rcx, [rcx+90h]; this
0x180040623  call    ?SetSelectionChanged@CCallMgr@@QEAAXXZ; CCallMgr::SetSelectionChanged(void)
0x180040628  mov     rcx, rbx; this
0x18004062b  call    ?CheckTableSelection@CTxtSelection@@QEAAXXZ; CTxtSelection::CheckTableSelection(void)
0x180040630  mov     eax, [rbx+58h]
0x180040633  mov     ecx, [rbx+70h]
0x180040636  mov     r15d, [rbx+28h]
0x18004063a  mov     r12d, [rbx+28h]
0x18004063e  sub     r15d, eax
0x180040641  mov     edx, [rbx+74h]
0x180040644  test    eax, eax
0x180040646  mov     eax, ecx
0x180040648  cmovs   r12d, r15d
0x18004064c  cmovs   r15d, [rbx+28h]
0x180040651  add     edx, ecx
0x180040653  cmp     ecx, edx
0x180040655  cmovge  eax, edx
0x180040658  cmp     r15d, eax
0x18004065b  jg      short loc_180040667
0x18004065d  cmp     ecx, edx
0x18004065f  cmovle  ecx, edx
0x180040662  cmp     r12d, ecx
0x180040665  jge     short loc_180040678
0x180040667  xor     edx, edx; int
0x180040669  mov     rcx, rbx; this
0x18004066c  call    ?ShowSelection@CTxtSelection@@QEAAHH@Z; CTxtSelection::ShowSelection(int)
0x180040671  or      dword ptr [rbx+88h], 8
0x180040678  mov     rax, [rbx+30h]
0x18004067c  and     dword ptr [rbx+88h], 0FFFFFFEEh
0x180040683  test    [rax+0B4h], r13d
0x18004068a  jnz     short loc_1800406B1
0x18004068c  mov     rcx, [rbx+68h]
0x180040690  or      r8d, 0FFFFFFFFh
0x180040694  mov     edx, r15d
0x180040697  mov     rax, [rcx]
0x18004069a  mov     rax, [rax+108h]
0x1800406a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800406a6  test    eax, eax
0x1800406a8  jnz     short loc_1800406B1
0x1800406aa  xor     edi, edi
0x1800406ac  jmp     loc_180040870
0x1800406b1  mov     rcx, [rsp+0B8h+arg_18]
0x1800406b9  xor     r13d, r13d
0x1800406bc  xor     r14d, r14d
0x1800406bf  shr     ebp, 4
0x1800406c2  test    rcx, rcx
0x1800406c5  jz      short loc_18004070E
0x1800406c7  cmp     [rsp+0B8h+arg_20], 1
0x1800406cf  jnz     short loc_1800406DB
0x1800406d1  mov     r8d, [rbx+28h]
0x1800406d5  mov     r9d, [rbx+58h]
0x1800406d9  jmp     short loc_1800406ED
0x1800406db  xor     r9d, r9d
0x1800406de  mov     r8d, r15d
0x1800406e1  cmp     [rsp+0B8h+arg_20], 3
0x1800406e9  cmovz   r8d, r12d
0x1800406ed  lea     eax, [r15+rsi]
0x1800406f1  mov     [rsp+0B8h+var_88], 1
0x1800406f9  mov     rdx, rcx
0x1800406fc  mov     dword ptr [rsp+0B8h+var_90], r13d
0x180040701  mov     rcx, [rbx+30h]
0x180040705  mov     [rsp+0B8h+var_98], eax
0x180040709  call    ?HandleSelectionAEInfo@@YAJPEAVCTxtEdit@@PEAVIUndoBuilder@@JJJJW4SELAE@@@Z; HandleSelectionAEInfo(CTxtEdit *,IUndoBuilder *,long,long,long,long,SELAE)
0x18004070e  mov     edx, [rbx+58h]
0x180040711  mov     r15d, 0FFFFFFFEh
0x180040717  cmp     edx, [rsp+0B8h+arg_8]
0x18004071e  jnz     short loc_18004076D
0x180040720  test    esi, esi
0x180040722  jnz     short loc_18004076D
0x180040724  neg     edx; int
0x180040726  lea     r13d, [r15+3]
0x18004072a  mov     rcx, rdi; this
0x18004072d  call    ?Advance@CRchTxtPtr@@QEAAJJ@Z; CRchTxtPtr::Advance(long)
0x180040732  mov     eax, [rbx+58h]
0x180040735  mov     ecx, 2000h
0x18004073a  neg     eax
0x18004073c  mov     [rbx+58h], eax
0x18004073f  mov     rax, [rbx+30h]
0x180040743  test    [rax+0B8h], cx
0x18004074a  jz      short loc_18004076D
0x18004074c  mov     rcx, rbx; this
0x18004074f  call    ?GetPF@CTxtSelection@@QEAAPEBVCParaFormat@@XZ; CTxtSelection::GetPF(void)
0x180040754  cmp     [rax+20h], r15w
0x180040759  jg      short loc_18004076D
0x18004075b  mov     rcx, rbx; this
0x18004075e  call    ?GetPF@CTxtSelection@@QEAAPEBVCParaFormat@@XZ; CTxtSelection::GetPF(void)
0x180040763  cmp     word ptr [rax+20h], 0FFF6h
0x180040768  jl      short loc_18004076D
0x18004076a  mov     r14d, r13d
0x18004076d  mov     eax, [rsp+0B8h+arg_30]
0x180040774  mov     edx, esi
0x180040776  mov     r9, [rsp+0B8h+arg_18]
0x18004077e  mov     rcx, rbx
0x180040781  mov     r8, [rsp+0B8h+arg_10]
0x180040789  mov     [rsp+0B8h+var_88], eax
0x18004078d  mov     rax, [rsp+0B8h+arg_28]
0x180040795  mov     [rsp+0B8h+var_90], rax
0x18004079a  mov     [rsp+0B8h+var_98], 0
0x1800407a2  call    ?ReplaceRange@CTxtRange@@UEAAJJPEBGPEAVIUndoBuilder@@W4SELRR@@PEAJK@Z; CTxtRange::ReplaceRange(long,ushort const *,IUndoBuilder *,SELRR,long *,ulong)
0x1800407a7  mov     ecx, [rbx+28h]
0x1800407aa  mov     edx, ebp
0x1800407ac  shl     edx, 4
0x1800407af  mov     edi, eax
0x1800407b1  mov     [rbx+70h], ecx
0x1800407b4  mov     ecx, [rbx+88h]
0x1800407ba  xor     edx, ecx
0x1800407bc  and     edx, 10h
0x1800407bf  mov     dword ptr [rbx+74h], 0
0x1800407c6  xor     edx, ecx
0x1800407c8  mov     [rbx+88h], edx
0x1800407ce  cmp     eax, esi
0x1800407d0  jnz     loc_180040870
0x1800407d6  test    r13d, r13d
0x1800407d9  jz      short loc_180040846
0x1800407db  or      esi, 0FFFFFFFFh
0x1800407de  mov     [rsp+0B8h+var_58], r15w
0x1800407e4  test    r14d, r14d
0x1800407e7  jnz     short loc_1800407EE
0x1800407e9  mov     [rsp+0B8h+var_58], si
0x1800407ee  mov     r9d, 400h; unsigned int
0x1800407f4  lea     rdx, [rsp+0B8h+var_78]; struct CParaFormat *
0x1800407f9  xor     r8d, r8d; struct IUndoBuilder *
0x1800407fc  mov     rcx, rbx; this
0x1800407ff  call    ?SetParaStyle@CTxtRange@@QEAAJPEBVCParaFormat@@PEAVIUndoBuilder@@K@Z; CTxtRange::SetParaStyle(CParaFormat const *,IUndoBuilder *,ulong)
0x180040804  mov     rax, [rbx+30h]
0x180040808  test    byte ptr [rax+0C0h], 1
0x18004080f  jz      short loc_18004083C
0x180040811  test    byte ptr [rax+0B4h], 80h
0x180040818  jz      short loc_180040846
0x18004081a  mov     ecx, 4000h
0x18004081f  test    [rax+0B8h], cx
0x180040826  jnz     short loc_180040846
0x180040828  mov     rcx, rbx; this
0x18004082b  call    ?MatchKeyboardToPara@CTxtSelection@@QEAAHXZ; CTxtSelection::MatchKeyboardToPara(void)
0x180040830  xor     edx, edx; unsigned int
0x180040832  mov     rcx, rbx; this
0x180040835  call    ?CheckSynchCharSet@CTxtSelection@@QEAAIK@Z; CTxtSelection::CheckSynchCharSet(ulong)
0x18004083a  jmp     short loc_180040846
0x18004083c  mov     edx, esi; int
0x18004083e  mov     rcx, rbx; this
0x180040841  call    ?Update_iFormat@CTxtRange@@QEAAXJ@Z; CTxtRange::Update_iFormat(long)
0x180040846  mov     rcx, [rbx+30h]
0x18004084a  mov     eax, [rcx+0B4h]
0x180040850  test    al, 8
0x180040852  jz      short loc_180040866
0x180040854  and     ebp, 1
0x180040857  xor     r8d, r8d; int
0x18004085a  mov     edx, ebp; int
0x18004085c  mov     rcx, rbx; this
0x18004085f  call    ?UpdateCaret@CTxtSelection@@QEAAHHH@Z; CTxtSelection::UpdateCaret(int,int)
0x180040864  jmp     short loc_180040870
0x180040866  bts     eax, 0Fh
0x18004086a  mov     [rcx+0B4h], eax
0x180040870  mov     eax, edi
0x180040872  mov     rbx, [rsp+0B8h+arg_0]
0x18004087a  add     rsp, 80h
0x180040881  pop     r15
0x180040883  pop     r14
0x180040885  pop     r13
0x180040887  pop     r12
0x180040889  pop     rdi
0x18004088a  pop     rsi
0x18004088b  pop     rbp
0x18004088c  retn
```
