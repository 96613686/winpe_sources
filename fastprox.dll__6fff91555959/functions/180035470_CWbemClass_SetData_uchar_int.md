# CWbemClass::SetData(uchar *,int)

- ea: `0x180035470`
- end: `0x180035aff`
- name: `?SetData@CWbemClass@@UEAAXPEAEH@Z`
- size: `1679`
- prototype: `void __fastcall(CWbemClass *__hidden this, unsigned __int8 *, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18001d860`
- `0x18001e0e0`
- `0x18001e490`
- `0x18001f5d0`
- `0x180035470`
- `0x180035b08`
- `0x18006fa4c`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18003592a`
- `wbemcomn!GetMemLogObject` at `0x180035993`
- `wbemcomn!GetMemLogObject` at `0x180035a3d`
- `wbemcomn!GetMemLogObject` at `0x180035a9e`
- `wbemcomn!GetMemLogObject` at `0x18003592a`
- `wbemcomn!GetMemLogObject` at `0x180035993`
- `wbemcomn!GetMemLogObject` at `0x180035a3d`
- `wbemcomn!GetMemLogObject` at `0x180035a9e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035938`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800359a1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035a4b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035aac`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035938`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800359a1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035a4b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035aac`

## pseudocode

```c
void __fastcall CWbemClass::SetData(CWbemClass *this, unsigned __int8 *a2, int a3)
{
  CDecorationPart *v5; // rbx
  unsigned __int8 *v6; // rax
  unsigned int v7; // r12d
  __int64 v8; // rax
  __int64 v9; // rdi
  __int64 v10; // rbx
  __int64 v11; // rax
  _DWORD *v12; // r8
  unsigned int v13; // esi
  _DWORD *v14; // rbx
  int NecessaryBytes; // eax
  int *v16; // r8
  int v17; // eax
  __int64 v18; // rdi
  __int64 v19; // rdx
  __int64 v20; // rax
  int *v21; // r8
  int v22; // eax
  __int64 v23; // r8
  unsigned int v24; // edx
  __int64 v25; // r8
  char *v26; // r14
  unsigned int *v27; // rsi
  unsigned __int64 v28; // r9
  unsigned __int64 v29; // rax
  __int64 v30; // r9
  __int64 v31; // rbx
  __int64 v32; // rax
  int *v33; // r8
  int v34; // edi
  unsigned int v35; // esi
  int *v36; // rbx
  int v37; // eax
  _QWORD *v38; // rdx
  int *v39; // r8
  int v40; // eax
  __int64 v41; // rdx
  __int64 v42; // rax
  int *v43; // r9
  int v44; // eax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v46; // rax
  CMemoryLog *v47; // rax
  CMemoryLog *v48; // rax
  int pExceptionObject; // [rsp+70h] [rbp+18h] BYREF
  unsigned int v50; // [rsp+78h] [rbp+20h]

  pExceptionObject = a3;
  if ( a3 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        167,
        WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
        "SafeIntException(ERROR_INVALID_PARAMETER)");
    }
    pExceptionObject = 87;
    throw (SafeIntException *)&pExceptionObject;
  }
  v5 = (CWbemClass *)((char *)this + 72);
  *((_QWORD *)this + 9) = a2;
  if ( (*a2 & 4) != 0 )
  {
    *((_QWORD *)this + 10) = a2 + 1;
    v6 = &a2[(int)CCompressedString::GetLength((CCompressedString *)(a2 + 1)) + 1];
  }
  else
  {
    *((_QWORD *)this + 10) = 0;
    v6 = 0;
  }
  *((_QWORD *)v5 + 2) = v6;
  if ( CDecorationPart::GetLength(v5) > a3 )
  {
    v46 = GetMemLogObject();
    CMemoryLog::Write(v46, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        168,
        WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
        "CX_Exception()");
    }
    throw (CX_Exception *)&pExceptionObject;
  }
  v7 = a3 - CDecorationPart::GetLength(v5);
  v8 = EndOf<CDecorationPart>(v5);
  *((_QWORD *)this + 62) = this;
  *((_QWORD *)this + 28) = v8;
  *((_QWORD *)this + 27) = 0;
  v9 = v8 + 13;
  *((_QWORD *)this + 26) = ((unsigned __int64)this + 168) & -(__int64)((CWbemClass *)((char *)this + 160) != 0);
  *((_QWORD *)this + 29) = v8 + 13;
  *((_DWORD *)this + 60) = -1;
  v10 = *(unsigned int *)(v8 + 13);
  v11 = (**((__int64 (__fastcall ***)(char *))this + 22))((char *)this + 176);
  *((_DWORD *)this + 64) = *(_DWORD *)(v10 + v9);
  *((_QWORD *)this + 34) = v11;
  *((_QWORD *)this + 33) = v9 + v10 + 4;
  *((_QWORD *)this + 37) = (char *)this + 176;
  *((_QWORD *)this + 38) = 0;
  *((_QWORD *)this + 36) = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 22) + 8LL))((char *)this + 176);
  v12 = (_DWORD *)(*((_QWORD *)this + 33) - 4LL + *((unsigned int *)this + 64));
  *((_QWORD *)this + 41) = v12;
  *((_QWORD *)this + 42) = ((unsigned __int64)this + 184) & -(__int64)((CWbemClass *)((char *)this + 176) != 0);
  LODWORD(v9) = *v12;
  v13 = *(_DWORD *)(*((_QWORD *)this + 28) + 9LL);
  v14 = &v12[2 * *v12 + 1];
  *((_QWORD *)this + 43) = v14;
  NecessaryBytes = CBitBlockTable<2>::GetNecessaryBytes(v9);
  *((_DWORD *)this + 90) = v13;
  *((_QWORD *)this + 44) = (char *)v14 + NecessaryBytes;
  *((_DWORD *)this + 91) = v9;
  *((_QWORD *)this + 46) = ((unsigned __int64)this + 192) & -(__int64)((CWbemClass *)((char *)this + 176) != 0);
  v16 = (int *)(*((_QWORD *)this + 43) + v13);
  *((_QWORD *)this + 51) = ((unsigned __int64)this + 200) & -(__int64)((CWbemClass *)((char *)this + 176) != 0);
  if ( *v16 >= 0 )
  {
    *((_QWORD *)this + 48) = v16;
    *((_QWORD *)this + 47) = v16 + 3;
  }
  else
  {
    *((_QWORD *)this + 47) = v16 + 1;
    *((_QWORD *)this + 48) = (char *)this + 392;
    v17 = *v16 & 0x7FFFFFFF;
    *((_DWORD *)this + 98) = v17;
    *((_DWORD *)this + 99) = v17;
    *(_DWORD *)(*((_QWORD *)this + 48) + 8LL) = 0;
  }
  v18 = 0;
  v19 = *((_QWORD *)this + 28) + **((unsigned int **)this + 28);
  *((_QWORD *)this + 60) = (char *)this + 160;
  *((_QWORD *)this + 61) = 0;
  *((_QWORD *)this + 53) = v19;
  *((_QWORD *)this + 54) = v19 + 8;
  v20 = *(unsigned __int16 *)(v19 + 4);
  *((_QWORD *)this + 59) = (char *)this + 416;
  v21 = (int *)(v19 + 8 * (v20 + 2 * v20 + 1));
  if ( *v21 >= 0 )
  {
    *((_QWORD *)this + 56) = v21;
    *((_QWORD *)this + 55) = v21 + 3;
  }
  else
  {
    *((_QWORD *)this + 55) = v21 + 1;
    *((_QWORD *)this + 56) = (char *)this + 456;
    v22 = *v21 & 0x7FFFFFFF;
    *((_DWORD *)this + 114) = v22;
    *((_DWORD *)this + 115) = v22;
    *(_DWORD *)(*((_QWORD *)this + 56) + 8LL) = 0;
  }
  v23 = *((_QWORD *)this + 28);
  v24 = **((_DWORD **)this + 53) + *((_QWORD *)this + 53) - v23;
  if ( v24 > v7 )
  {
    v47 = GetMemLogObject();
    CMemoryLog::Write(v47, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        169,
        WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
        "CX_Exception()");
    }
    throw (CX_Exception *)&pExceptionObject;
  }
  v25 = v24 + v23;
  v50 = v7 - v24;
  v26 = (char *)this + 520;
  *((_QWORD *)this + 105) = this;
  *((_QWORD *)this + 71) = v25;
  v27 = (unsigned int *)(v25 + 13);
  v28 = ((unsigned __int64)this + 176) & -(__int64)((CWbemClass *)((char *)this + 160) != 0);
  *((_QWORD *)this + 70) = v28;
  v29 = v28 + 72;
  *((_QWORD *)this + 69) = ((unsigned __int64)this + 512) & -(__int64)((CWbemClass *)((char *)this + 504) != 0);
  v30 = -(__int64)v28;
  *((_QWORD *)this + 72) = v25 + 13;
  *((_DWORD *)this + 146) = -1;
  if ( (v29 & -(__int64)(v30 != 0)) != 0 )
    v18 = (v29 & -(__int64)(v30 != 0)) + 8;
  v31 = *v27;
  v32 = (**(__int64 (__fastcall ***)(char *))v26)((char *)this + 520);
  *((_DWORD *)this + 150) = *(unsigned int *)((char *)v27 + v31);
  *((_QWORD *)this + 77) = v32;
  *((_QWORD *)this + 76) = (char *)v27 + v31 + 4;
  *((_QWORD *)this + 80) = (char *)this + 520;
  *((_QWORD *)this + 81) = v18;
  *((_QWORD *)this + 79) = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v26 + 8LL))((char *)this + 520);
  v33 = (int *)(*((_QWORD *)this + 76) - 4LL + *((unsigned int *)this + 150));
  *((_QWORD *)this + 84) = v33;
  *((_QWORD *)this + 85) = ((unsigned __int64)this + 528) & -(__int64)((CWbemClass *)((char *)this + 520) != 0);
  v34 = *v33;
  v35 = *(_DWORD *)(*((_QWORD *)this + 71) + 9LL);
  v36 = &v33[2 * *v33 + 1];
  *((_QWORD *)this + 86) = v36;
  v37 = CBitBlockTable<2>::GetNecessaryBytes(v34);
  *((_DWORD *)this + 176) = v35;
  *((_QWORD *)this + 87) = (char *)v36 + v37;
  *((_DWORD *)this + 177) = v34;
  v38 = (_QWORD *)((char *)this + 720);
  *((_QWORD *)this + 89) = ((unsigned __int64)this + 536) & -(__int64)((CWbemClass *)((char *)this + 520) != 0);
  v39 = (int *)(*((_QWORD *)this + 86) + v35);
  *((_QWORD *)this + 94) = ((unsigned __int64)this + 544) & -(__int64)(v26 != 0);
  if ( *v39 >= 0 )
  {
    *((_QWORD *)this + 91) = v39;
    *v38 = v39 + 3;
  }
  else
  {
    *v38 = v39 + 1;
    *((_QWORD *)this + 91) = (char *)this + 736;
    v40 = *v39 & 0x7FFFFFFF;
    *((_DWORD *)this + 184) = v40;
    *((_DWORD *)this + 185) = v40;
    *(_DWORD *)(*((_QWORD *)this + 91) + 8LL) = 0;
  }
  v41 = *((_QWORD *)this + 71) + **((unsigned int **)this + 71);
  *((_QWORD *)this + 103) = (char *)this + 504;
  *((_QWORD *)this + 96) = v41;
  *((_QWORD *)this + 104) = ((unsigned __int64)this + 416) & -(__int64)((CWbemClass *)((char *)this + 160) != 0);
  *((_QWORD *)this + 97) = v41 + 8;
  v42 = *(unsigned __int16 *)(v41 + 4);
  *((_QWORD *)this + 102) = (char *)this + 760;
  v43 = (int *)(v41 + 8 * (v42 + 2 * v42 + 1));
  if ( *v43 >= 0 )
  {
    *((_QWORD *)this + 99) = v43;
    *((_QWORD *)this + 98) = v43 + 3;
  }
  else
  {
    *((_QWORD *)this + 98) = v43 + 1;
    *((_QWORD *)this + 99) = (char *)this + 800;
    v44 = *v43 & 0x7FFFFFFF;
    *((_DWORD *)this + 200) = v44;
    *((_DWORD *)this + 201) = v44;
    *(_DWORD *)(*((_QWORD *)this + 99) + 8LL) = 0;
  }
  if ( **((_DWORD **)this + 96) + (unsigned int)*((_QWORD *)this + 96) - *((_DWORD *)this + 142) > v50 )
  {
    v48 = GetMemLogObject();
    CMemoryLog::Write(v48, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        170,
        WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
        "CX_Exception()");
    }
    throw (CX_Exception *)&pExceptionObject;
  }
  *((_DWORD *)this + 38) = pExceptionObject;
}

```

## disassembly

```asm
0x180035470  mov     [rsp+arg_0], rbx
0x180035475  mov     [rsp+pExceptionObject], r8d
0x18003547a  push    rbp
0x18003547b  push    rsi
0x18003547c  push    rdi
0x18003547d  push    r12
0x18003547f  push    r13
0x180035481  push    r14
0x180035483  push    r15
0x180035485  sub     rsp, 20h
0x180035489  xor     ebp, ebp
0x18003548b  mov     esi, r8d
0x18003548e  mov     rdi, rdx
0x180035491  mov     r13, rcx
0x180035494  test    r8d, r8d
0x180035497  js      loc_18003592A
0x18003549d  lea     rbx, [rcx+48h]
0x1800354a1  mov     [rbx], rdx
0x1800354a4  test    byte ptr [rdx], 4
0x1800354a7  jnz     loc_180035907
0x1800354ad  mov     [rbx+8], rbp
0x1800354b1  mov     eax, ebp
0x1800354b3  mov     rcx, rbx; this
0x1800354b6  mov     [rbx+10h], rax
0x1800354ba  call    ?GetLength@CDecorationPart@@QEAAKXZ; CDecorationPart::GetLength(void)
0x1800354bf  cmp     eax, esi
0x1800354c1  ja      loc_180035993
0x1800354c7  mov     rcx, rbx; this
0x1800354ca  call    ?GetLength@CDecorationPart@@QEAAKXZ; CDecorationPart::GetLength(void)
0x1800354cf  mov     r12d, esi
0x1800354d2  lea     r14, [r13+0A0h]
0x1800354d9  mov     rcx, rbx
0x1800354dc  sub     r12d, eax
0x1800354df  call    ??$EndOf@VCDecorationPart@@@@YAPEAEAEAVCDecorationPart@@@Z; EndOf<CDecorationPart>(CDecorationPart &)
0x1800354e4  mov     [r14+150h], r13
0x1800354eb  lea     r15, [r14+10h]
0x1800354ef  mov     [r15+30h], rax
0x1800354f3  lea     r8, [r14+8]
0x1800354f7  mov     [r15+28h], rbp
0x1800354fb  mov     rcx, r14
0x1800354fe  lea     rdi, [rax+0Dh]
0x180035502  neg     rcx
0x180035505  mov     rcx, r15
0x180035508  sbb     rdx, rdx
0x18003550b  and     rdx, r8
0x18003550e  mov     [r15+20h], rdx
0x180035512  mov     [r15+38h], rdi
0x180035516  mov     dword ptr [r15+40h], 0FFFFFFFFh
0x18003551e  mov     rax, [r15]
0x180035521  mov     ebx, [rdi]
0x180035523  mov     rax, [rax]
0x180035526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003552b  mov     ecx, [rbx+rdi]
0x18003552e  mov     [r15+50h], ecx
0x180035532  lea     rcx, [rbx+4]
0x180035536  mov     [r15+60h], rax
0x18003553a  add     rcx, rdi
0x18003553d  mov     [r15+58h], rcx
0x180035541  mov     rcx, r15
0x180035544  mov     [r15+78h], r15
0x180035548  mov     [r15+80h], rbp
0x18003554f  mov     rax, [r15]
0x180035552  mov     rax, [rax+8]
0x180035556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003555b  mov     [r15+70h], rax
0x18003555f  lea     rdx, [r15+8]
0x180035563  mov     rax, [r15+58h]
0x180035567  mov     r8d, [r15+50h]
0x18003556b  add     rax, 0FFFFFFFFFFFFFFFCh
0x18003556f  add     r8, rax
0x180035572  mov     rax, r15
0x180035575  mov     [r15+98h], r8
0x18003557c  neg     rax
0x18003557f  sbb     rcx, rcx
0x180035582  and     rcx, rdx
0x180035585  mov     [r15+0A0h], rcx
0x18003558c  mov     rax, [r15+30h]
0x180035590  mov     edi, [r8]
0x180035593  mov     ecx, edi
0x180035595  mov     esi, [rax+9]
0x180035598  lea     eax, ds:4[rdi*8]
0x18003559f  movsxd  rbx, eax
0x1800355a2  add     rbx, r8
0x1800355a5  mov     [r15+0A8h], rbx
0x1800355ac  call    ?GetNecessaryBytes@?$CBitBlockTable@$01@@SAHH@Z; CBitBlockTable<2>::GetNecessaryBytes(int)
0x1800355b1  movsxd  rcx, eax
0x1800355b4  lea     rdx, [r15+10h]
0x1800355b8  add     rcx, rbx
0x1800355bb  mov     [r15+0B8h], esi
0x1800355c2  mov     [r15+0B0h], rcx
0x1800355c9  mov     rax, r15
0x1800355cc  neg     rax
0x1800355cf  mov     [r15+0BCh], edi
0x1800355d6  mov     r8d, esi
0x1800355d9  mov     rax, r15
0x1800355dc  sbb     rcx, rcx
0x1800355df  mov     r9d, 7FFFFFFFh
0x1800355e5  and     rcx, rdx
0x1800355e8  lea     rdx, [r15+18h]
0x1800355ec  mov     [r15+0C0h], rcx
0x1800355f3  add     r8, [r15+0A8h]
0x1800355fa  neg     rax
0x1800355fd  sbb     rcx, rcx
0x180035600  and     rcx, rdx
0x180035603  mov     [r15+0E8h], rcx
0x18003560a  cmp     [r8], ebp
0x18003560d  jge     loc_1800359F4
0x180035613  lea     rax, [r8+4]
0x180035617  mov     [r15+0C8h], rax
0x18003561e  lea     rcx, [r15+0D8h]
0x180035625  mov     [r15+0D0h], rcx
0x18003562c  mov     eax, [r8]
0x18003562f  and     eax, r9d
0x180035632  mov     [rcx], eax
0x180035634  mov     [rcx+4], eax
0x180035637  mov     rax, [r15+0D0h]
0x18003563e  mov     [rax+8], ebp
0x180035641  mov     rcx, [r14+40h]
0x180035645  lea     rbp, [r14+100h]
0x18003564c  xor     edi, edi
0x18003564e  mov     edx, [rcx]
0x180035650  add     rdx, rcx
0x180035653  mov     [rbp+40h], r14
0x180035657  mov     [rbp+48h], rdi
0x18003565b  mov     [rbp+8], rdx
0x18003565f  lea     rax, [rdx+8]
0x180035663  mov     [rbp+10h], rax
0x180035667  movzx   eax, word ptr [rdx+4]
0x18003566b  mov     [rbp+38h], rbp
0x18003566f  lea     r8, ds:1[rax*2]
0x180035677  add     r8, rax
0x18003567a  lea     r8, [rdx+r8*8]
0x18003567e  cmp     [r8], edi
0x180035681  jge     loc_180035A2C
0x180035687  lea     rax, [r8+4]
0x18003568b  mov     [rbp+18h], rax
0x18003568f  lea     rcx, [rbp+28h]
0x180035693  mov     [rbp+20h], rcx
0x180035697  mov     eax, [r8]
0x18003569a  and     eax, r9d
0x18003569d  mov     [rcx], eax
0x18003569f  mov     [rcx+4], eax
0x1800356a2  mov     rax, [rbp+20h]
0x1800356a6  mov     [rax+8], edi
0x1800356a9  mov     rax, [r13+1A8h]
0x1800356b0  mov     r8, [r13+0E0h]
0x1800356b7  mov     edx, eax
0x1800356b9  sub     edx, r8d
0x1800356bc  add     edx, [rax]
0x1800356be  cmp     edx, r12d
0x1800356c1  ja      loc_180035A3D
0x1800356c7  sub     r12d, edx
0x1800356ca  mov     eax, edx
0x1800356cc  add     r8, rax
0x1800356cf  mov     [rsp+58h+arg_18], r12d
0x1800356d4  lea     r12, [r13+1F8h]
0x1800356db  lea     r14, [r12+10h]
0x1800356e0  mov     [r12+150h], r13
0x1800356e8  mov     [r14+30h], r8
0x1800356ec  lea     rax, [r13+0A0h]
0x1800356f3  neg     rax
0x1800356f6  lea     rdx, [r12+8]
0x1800356fb  mov     rax, r12
0x1800356fe  lea     rsi, [r8+0Dh]
0x180035702  sbb     r9, r9
0x180035705  and     r9, r15
0x180035708  neg     rax
0x18003570b  mov     [r14+28h], r9
0x18003570f  sbb     rcx, rcx
0x180035712  and     rcx, rdx
0x180035715  lea     rax, [r9+48h]
0x180035719  mov     [r14+20h], rcx
0x18003571d  neg     r9
0x180035720  mov     [r14+38h], rsi
0x180035724  sbb     rcx, rcx
0x180035727  mov     dword ptr [r14+40h], 0FFFFFFFFh
0x18003572f  and     rcx, rax
0x180035732  jnz     loc_180035921
0x180035738  mov     rax, [r14]
0x18003573b  mov     rcx, r14
0x18003573e  mov     ebx, [rsi]
0x180035740  mov     rax, [rax]
0x180035743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035748  mov     ecx, [rbx+rsi]
0x18003574b  mov     [r14+50h], ecx
0x18003574f  lea     rcx, [rbx+4]
0x180035753  mov     [r14+60h], rax
0x180035757  add     rcx, rsi
0x18003575a  mov     [r14+58h], rcx
0x18003575e  mov     rcx, r14
0x180035761  mov     [r14+78h], r14
0x180035765  mov     [r14+80h], rdi
0x18003576c  mov     rax, [r14]
0x18003576f  mov     rax, [rax+8]
0x180035773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035778  mov     [r14+70h], rax
0x18003577c  lea     rdx, [r14+8]
0x180035780  mov     rax, [r14+58h]
0x180035784  mov     r8d, [r14+50h]
0x180035788  add     rax, 0FFFFFFFFFFFFFFFCh
0x18003578c  add     r8, rax
0x18003578f  mov     rax, r14
0x180035792  mov     [r14+98h], r8
0x180035799  neg     rax
0x18003579c  sbb     rcx, rcx
0x18003579f  and     rcx, rdx
0x1800357a2  mov     [r14+0A0h], rcx
0x1800357a9  mov     rax, [r14+30h]
0x1800357ad  mov     edi, [r8]
0x1800357b0  mov     ecx, edi
0x1800357b2  mov     esi, [rax+9]
0x1800357b5  lea     eax, ds:4[rdi*8]
0x1800357bc  movsxd  rbx, eax
0x1800357bf  add     rbx, r8
0x1800357c2  mov     [r14+0A8h], rbx
0x1800357c9  call    ?GetNecessaryBytes@?$CBitBlockTable@$01@@SAHH@Z; CBitBlockTable<2>::GetNecessaryBytes(int)
0x1800357ce  movsxd  rcx, eax
0x1800357d1  lea     rdx, [r14+10h]
0x1800357d5  add     rcx, rbx
0x1800357d8  mov     [r14+0B8h], esi
0x1800357df  mov     [r14+0B0h], rcx
0x1800357e6  mov     rax, r14
0x1800357e9  neg     rax
0x1800357ec  mov     [r14+0BCh], edi
0x1800357f3  mov     r8d, esi
0x1800357f6  sbb     rcx, rcx
0x1800357f9  and     rcx, rdx
0x1800357fc  lea     rdx, [r14+0C8h]
0x180035803  mov     [r14+0C0h], rcx
0x18003580a  lea     rcx, [r14+18h]
0x18003580e  add     r8, [r14+0A8h]
0x180035815  neg     r14
0x180035818  sbb     rax, rax
0x18003581b  xor     r10d, r10d
0x18003581e  and     rax, rcx
0x180035821  mov     [rdx+20h], rax
0x180035825  cmp     [r8], r10d
0x180035828  jge     loc_180035A0B
0x18003582e  lea     rax, [r8+4]
0x180035832  mov     [rdx], rax
0x180035835  lea     rcx, [rdx+10h]
0x180035839  mov     [rdx+8], rcx
0x18003583d  mov     eax, [r8]
0x180035840  btr     eax, 1Fh
0x180035844  mov     [rcx], eax
0x180035846  mov     [rcx+4], eax
0x180035849  mov     rax, [rdx+8]
0x18003584d  mov     [rax+8], r10d
0x180035851  mov     rcx, [r12+40h]
0x180035856  lea     r8, [r12+100h]
0x18003585e  lea     rax, [r13+0A0h]
0x180035865  mov     edx, [rcx]
0x180035867  add     rdx, rcx
0x18003586a  mov     [r8+40h], r12
0x18003586e  neg     rax
0x180035871  mov     [r8+8], rdx
0x180035875  sbb     rax, rax
0x180035878  and     rax, rbp
0x18003587b  mov     [r8+48h], rax
0x18003587f  lea     rax, [rdx+8]
0x180035883  mov     [r8+10h], rax
0x180035887  movzx   eax, word ptr [rdx+4]
0x18003588b  mov     [r8+38h], r8
0x18003588f  lea     r9, ds:1[rax*2]
0x180035897  add     r9, rax
0x18003589a  lea     r9, [rdx+r9*8]
0x18003589e  cmp     [r9], r10d
0x1800358a1  jge     loc_180035A1B
0x1800358a7  lea     rax, [r9+4]
0x1800358ab  mov     [r8+18h], rax
0x1800358af  lea     rcx, [r8+28h]
0x1800358b3  mov     [r8+20h], rcx
0x1800358b7  mov     eax, [r9]
0x1800358ba  btr     eax, 1Fh
0x1800358be  mov     [rcx], eax
0x1800358c0  mov     [rcx+4], eax
0x1800358c3  mov     rax, [r8+20h]
0x1800358c7  mov     [rax+8], r10d
0x1800358cb  mov     rax, [r13+300h]
0x1800358d2  mov     ecx, eax
0x1800358d4  sub     ecx, [r13+238h]
0x1800358db  add     ecx, [rax]
0x1800358dd  cmp     ecx, [rsp+58h+arg_18]
0x1800358e1  ja      loc_180035A9E
0x1800358e7  mov     eax, [rsp+58h+pExceptionObject]
0x1800358eb  mov     rbx, [rsp+58h+arg_0]
0x1800358f0  mov     [r13+98h], eax
0x1800358f7  add     rsp, 20h
0x1800358fb  pop     r15
0x1800358fd  pop     r14
0x1800358ff  pop     r13
0x180035901  pop     r12
0x180035903  pop     rdi
0x180035904  pop     rsi
0x180035905  pop     rbp
0x180035906  retn
0x180035907  lea     rcx, [rdx+1]; this
0x18003590b  mov     [rbx+8], rcx
0x18003590f  call    ?GetLength@CCompressedString@@QEBAHXZ; CCompressedString::GetLength(void)
0x180035914  cdqe
  ... truncated ...
```
