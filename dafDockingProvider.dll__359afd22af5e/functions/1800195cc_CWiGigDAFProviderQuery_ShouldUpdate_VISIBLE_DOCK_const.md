# CWiGigDAFProviderQuery::ShouldUpdate(_VISIBLE_DOCK const &)

- ea: `0x1800195cc`
- end: `0x1800198fa`
- name: `?ShouldUpdate@CWiGigDAFProviderQuery@@AEAA_NAEBU_VISIBLE_DOCK@@@Z`
- size: `814`
- prototype: `char __fastcall(CWiGigDAFProviderQuery *this, const struct _VISIBLE_DOCK *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180018fc0`

## callees

- `0x18000cb40`
- `0x180013b24`
- `0x1800184f8`
- `0x180018540`
- `0x1800195cc`
- `0x18001a18c`
- `0x18001ca70`

## pseudocode

```c
char __fastcall CWiGigDAFProviderQuery::ShouldUpdate(CWiGigDAFProviderQuery *this, const struct _VISIBLE_DOCK *a2)
{
  const struct _VISIBLE_DOCK *v2; // rbx
  __int64 v4; // rdx
  char *v5; // r14
  _QWORD *v6; // rcx
  _OWORD *v7; // rax
  __int64 v8; // rsi
  __int64 v9; // rdx
  unsigned __int8 *v10; // rbx
  _OWORD *v11; // rax
  _OWORD *v12; // rcx
  __int64 v13; // rax
  __int64 v15; // rax
  unsigned __int64 v16; // [rsp+30h] [rbp-4F8h] BYREF
  unsigned __int8 v17; // [rsp+38h] [rbp-4F0h]
  unsigned __int8 v18; // [rsp+39h] [rbp-4EFh]
  unsigned __int8 v19; // [rsp+3Ah] [rbp-4EEh]
  char v20; // [rsp+3Bh] [rbp-4EDh]
  unsigned __int8 v21; // [rsp+3Ch] [rbp-4ECh]
  unsigned __int8 v22; // [rsp+3Dh] [rbp-4EBh]
  CWiGigDAFProviderQuery *v23; // [rsp+40h] [rbp-4E8h]
  _QWORD v24[3]; // [rsp+48h] [rbp-4E0h] BYREF
  unsigned __int8 v25[8]; // [rsp+60h] [rbp-4C8h] BYREF
  _BYTE v26[1160]; // [rsp+68h] [rbp-4C0h] BYREF

  v2 = a2;
  v23 = this;
  v17 = *((_BYTE *)a2 + 528);
  v18 = *((_BYTE *)a2 + 529);
  v19 = *((_BYTE *)a2 + 530);
  v4 = *((unsigned __int8 *)a2 + 531);
  v20 = v4;
  v21 = *((_BYTE *)v2 + 532);
  v22 = *((_BYTE *)v2 + 533);
  v16 = v22 | ((v21 | ((v4 | ((v19 | ((v18 | ((unsigned __int64)v17 << 8)) << 8)) << 8)) << 8)) << 8);
  v5 = (char *)this + 112;
  std::_Hash<std::tr1::_Umap_traits<HardwareAddress,VisibleDock,std::_Hash_compare<HardwareAddress,std::hash<HardwareAddress>,std::equal_to<HardwareAddress>>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>,0>>::lower_bound(
    (char *)this + 112,
    v24,
    &v16);
  v25[0] = 1;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_29db95f43f0434e41d7a9cbe58adf31d_Traceguids, v25, v2, 1);
    v6 = WPP_GLOBAL_Control;
  }
  v7 = v26;
  v8 = 9;
  v9 = 9;
  do
  {
    *v7 = *(_OWORD *)v2;
    v7[1] = *((_OWORD *)v2 + 1);
    v7[2] = *((_OWORD *)v2 + 2);
    v7[3] = *((_OWORD *)v2 + 3);
    v7[4] = *((_OWORD *)v2 + 4);
    v7[5] = *((_OWORD *)v2 + 5);
    v7[6] = *((_OWORD *)v2 + 6);
    v7[7] = *((_OWORD *)v2 + 7);
    v7 += 8;
    v2 = (const struct _VISIBLE_DOCK *)((char *)v2 + 128);
    --v9;
  }
  while ( v9 );
  if ( v6 != &WPP_GLOBAL_Control && *((_BYTE *)v6 + 25) >= 3u && (*((_BYTE *)v6 + 28) & 1) != 0 )
    WPP_SF_qS(v6[2], 27, (unsigned int)&WPP_29db95f43f0434e41d7a9cbe58adf31d_Traceguids, (_DWORD)this, (__int64)v26);
  v10 = (unsigned __int8 *)std::tr1::unordered_map<HardwareAddress,VisibleDock,std::hash<HardwareAddress>,std::equal_to<HardwareAddress>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>::operator[](
                             v5,
                             &v16);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qqd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      &WPP_29db95f43f0434e41d7a9cbe58adf31d_Traceguids,
      v10,
      v25,
      v25[0]);
  }
  *v10 = v25[0];
  v11 = v10 + 8;
  v12 = v26;
  do
  {
    *v11 = *v12;
    v11[1] = v12[1];
    v11[2] = v12[2];
    v11[3] = v12[3];
    v11[4] = v12[4];
    v11[5] = v12[5];
    v11[6] = v12[6];
    v11[7] = v12[7];
    v11 += 8;
    v12 += 8;
    --v8;
  }
  while ( v8 );
  if ( v24[0] == *((_QWORD *)this + 15) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = std::tr1::unordered_map<HardwareAddress,VisibleDock,std::hash<HardwareAddress>,std::equal_to<HardwareAddress>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>::operator[](
              v5,
              &v16);
      WPP_SF_qS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        (unsigned int)&WPP_29db95f43f0434e41d7a9cbe58adf31d_Traceguids,
        (_DWORD)this,
        v15 + 8);
    }
    VisibleDock::~VisibleDock((VisibleDock *)v25);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = std::tr1::unordered_map<HardwareAddress,VisibleDock,std::hash<HardwareAddress>,std::equal_to<HardwareAddress>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>::operator[](
              v5,
              &v16);
      WPP_SF_qS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        (unsigned int)&WPP_29db95f43f0434e41d7a9cbe58adf31d_Traceguids,
        (_DWORD)this,
        v13 + 8);
    }
    VisibleDock::~VisibleDock((VisibleDock *)v25);
    return 1;
  }
}

```

## disassembly

```asm
0x1800195cc  mov     [rsp+arg_10], rbx
0x1800195d1  push    rsi
0x1800195d2  push    rdi
0x1800195d3  push    r12
0x1800195d5  push    r13
0x1800195d7  push    r14
0x1800195d9  sub     rsp, 500h
0x1800195e0  mov     rax, cs:__security_cookie
0x1800195e7  xor     rax, rsp
0x1800195ea  mov     [rsp+528h+var_38], rax
0x1800195f2  mov     rbx, rdx
0x1800195f5  mov     rdi, rcx
0x1800195f8  mov     [rsp+528h+var_4E8], rcx
0x1800195fd  movzx   r10d, byte ptr [rdx+210h]
0x180019605  mov     [rsp+528h+var_4F0], r10b
0x18001960a  movzx   eax, byte ptr [rdx+211h]
0x180019611  mov     [rsp+528h+var_4EF], al
0x180019615  movzx   ecx, byte ptr [rdx+212h]
0x18001961c  mov     [rsp+528h+var_4EE], cl
0x180019620  movzx   edx, byte ptr [rdx+213h]
0x180019627  mov     [rsp+528h+var_4ED], dl
0x18001962b  movzx   r8d, byte ptr [rbx+214h]
0x180019633  mov     [rsp+528h+var_4EC], r8b
0x180019638  movzx   r9d, byte ptr [rbx+215h]
0x180019640  mov     [rsp+528h+var_4EB], r9b
0x180019645  shl     r10, 8
0x180019649  or      r10, rax
0x18001964c  shl     r10, 8
0x180019650  or      r10, rcx
0x180019653  shl     r10, 8
0x180019657  or      r10, rdx
0x18001965a  shl     r10, 8
0x18001965e  or      r10, r8
0x180019661  shl     r10, 8
0x180019665  or      r10, r9
0x180019668  mov     [rsp+528h+var_4F8], r10
0x18001966d  lea     r14, [rdi+70h]
0x180019671  lea     r8, [rsp+528h+var_4F8]
0x180019676  lea     rdx, [rsp+528h+var_4E0]
0x18001967b  mov     rcx, r14
0x18001967e  call    ?lower_bound@?$_Hash@V?$_Umap_traits@VHardwareAddress@@VVisibleDock@@V?$_Hash_compare@VHardwareAddress@@V?$hash@VHardwareAddress@@@std@@U?$equal_to@VHardwareAddress@@@3@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@4@$0A@@tr1@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@2@AEBVHardwareAddress@@@Z; std::_Hash<std::tr1::_Umap_traits<HardwareAddress,VisibleDock,std::_Hash_compare<HardwareAddress,std::hash<HardwareAddress>,std::equal_to<HardwareAddress>>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>,0>>::lower_bound(HardwareAddress const &)
0x180019683  mov     [rsp+528h+var_4C8], 1
0x180019688  lea     r12, WPP_GLOBAL_Control
0x18001968f  mov     rcx, cs:WPP_GLOBAL_Control
0x180019696  cmp     rcx, r12
0x180019699  jz      short loc_1800196D5
0x18001969b  cmp     byte ptr [rcx+19h], 4
0x18001969f  jb      short loc_1800196D5
0x1800196a1  test    byte ptr [rcx+1Ch], 1
0x1800196a5  jz      short loc_1800196D5
0x1800196a7  mov     edx, 0Ch
0x1800196ac  mov     [rsp+528h+var_500], 1
0x1800196b4  mov     [rsp+528h+var_508], rbx
0x1800196b9  lea     r9, [rsp+528h+var_4C8]
0x1800196be  lea     r8, WPP_29db95f43f0434e41d7a9cbe58adf31d_Traceguids
0x1800196c5  mov     rcx, [rcx+10h]
0x1800196c9  call    WPP_SF_qqd
0x1800196ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800196d5  lea     rax, [rsp+528h+var_4C0]
0x1800196da  mov     esi, 9
0x1800196df  mov     edx, esi
0x1800196e1  lea     r13d, [rsi+77h]
0x1800196e5  movups  xmm0, xmmword ptr [rbx]
0x1800196e8  movups  xmmword ptr [rax], xmm0
0x1800196eb  movups  xmm1, xmmword ptr [rbx+10h]
0x1800196ef  movups  xmmword ptr [rax+10h], xmm1
0x1800196f3  movups  xmm0, xmmword ptr [rbx+20h]
0x1800196f7  movups  xmmword ptr [rax+20h], xmm0
0x1800196fb  movups  xmm1, xmmword ptr [rbx+30h]
0x1800196ff  movups  xmmword ptr [rax+30h], xmm1
0x180019703  movups  xmm0, xmmword ptr [rbx+40h]
0x180019707  movups  xmmword ptr [rax+40h], xmm0
0x18001970b  movups  xmm1, xmmword ptr [rbx+50h]
0x18001970f  movups  xmmword ptr [rax+50h], xmm1
0x180019713  movups  xmm0, xmmword ptr [rbx+60h]
0x180019717  movups  xmmword ptr [rax+60h], xmm0
0x18001971b  movups  xmm1, xmmword ptr [rbx+70h]
0x18001971f  movups  xmmword ptr [rax+70h], xmm1
0x180019723  add     rax, r13
0x180019726  add     rbx, r13
0x180019729  sub     rdx, 1
0x18001972d  jnz     short loc_1800196E5
0x18001972f  cmp     rcx, r12
0x180019732  jz      short loc_180019762
0x180019734  cmp     byte ptr [rcx+19h], 3
0x180019738  jb      short loc_180019762
0x18001973a  test    byte ptr [rcx+1Ch], 1
0x18001973e  jz      short loc_180019762
0x180019740  mov     edx, 1Bh
0x180019745  lea     rax, [rsp+528h+var_4C0]
0x18001974a  mov     [rsp+528h+var_508], rax
0x18001974f  mov     r9, rdi
0x180019752  lea     r8, WPP_29db95f43f0434e41d7a9cbe58adf31d_Traceguids
0x180019759  mov     rcx, [rcx+10h]
0x18001975d  call    WPP_SF_qS
0x180019762  lea     rdx, [rsp+528h+var_4F8]
0x180019767  mov     rcx, r14
0x18001976a  call    ??A?$unordered_map@VHardwareAddress@@VVisibleDock@@V?$hash@VHardwareAddress@@@std@@U?$equal_to@VHardwareAddress@@@4@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@4@@tr1@std@@QEAAAEAVVisibleDock@@AEBVHardwareAddress@@@Z; std::tr1::unordered_map<HardwareAddress,VisibleDock,std::hash<HardwareAddress>,std::equal_to<HardwareAddress>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>::operator[](HardwareAddress const &)
0x18001976f  mov     rbx, rax
0x180019772  mov     rcx, cs:WPP_GLOBAL_Control
0x180019779  cmp     rcx, r12
0x18001977c  jz      short loc_1800197B5
0x18001977e  cmp     byte ptr [rcx+19h], 4
0x180019782  jb      short loc_1800197B5
0x180019784  test    byte ptr [rcx+1Ch], 1
0x180019788  jz      short loc_1800197B5
0x18001978a  movzx   eax, [rsp+528h+var_4C8]
0x18001978f  mov     edx, 0Fh
0x180019794  mov     [rsp+528h+var_500], eax
0x180019798  lea     rax, [rsp+528h+var_4C8]
0x18001979d  mov     [rsp+528h+var_508], rax
0x1800197a2  mov     r9, rbx
0x1800197a5  lea     r8, WPP_29db95f43f0434e41d7a9cbe58adf31d_Traceguids
0x1800197ac  mov     rcx, [rcx+10h]
0x1800197b0  call    WPP_SF_qqd
0x1800197b5  mov     al, [rsp+528h+var_4C8]
0x1800197b9  mov     [rbx], al
0x1800197bb  lea     rax, [rbx+8]
0x1800197bf  lea     rcx, [rsp+528h+var_4C0]
0x1800197c4  movups  xmm0, xmmword ptr [rcx]
0x1800197c7  movups  xmmword ptr [rax], xmm0
0x1800197ca  movups  xmm1, xmmword ptr [rcx+10h]
0x1800197ce  movups  xmmword ptr [rax+10h], xmm1
0x1800197d2  movups  xmm0, xmmword ptr [rcx+20h]
0x1800197d6  movups  xmmword ptr [rax+20h], xmm0
0x1800197da  movups  xmm1, xmmword ptr [rcx+30h]
0x1800197de  movups  xmmword ptr [rax+30h], xmm1
0x1800197e2  movups  xmm0, xmmword ptr [rcx+40h]
0x1800197e6  movups  xmmword ptr [rax+40h], xmm0
0x1800197ea  movups  xmm1, xmmword ptr [rcx+50h]
0x1800197ee  movups  xmmword ptr [rax+50h], xmm1
0x1800197f2  movups  xmm0, xmmword ptr [rcx+60h]
0x1800197f6  movups  xmmword ptr [rax+60h], xmm0
0x1800197fa  movups  xmm1, xmmword ptr [rcx+70h]
0x1800197fe  movups  xmmword ptr [rax+70h], xmm1
0x180019802  add     rax, r13
0x180019805  add     rcx, r13
0x180019808  sub     rsi, 1
0x18001980c  jnz     short loc_1800197C4
0x18001980e  mov     rax, [rdi+78h]
0x180019812  cmp     [rsp+528h+var_4E0], rax
0x180019817  jz      short loc_180019873
0x180019819  mov     rax, cs:WPP_GLOBAL_Control
0x180019820  cmp     rax, r12
0x180019823  jz      short loc_180019865
0x180019825  cmp     byte ptr [rax+19h], 3
0x180019829  jb      short loc_180019865
0x18001982b  test    byte ptr [rax+1Ch], 1
0x18001982f  jz      short loc_180019865
0x180019831  lea     rdx, [rsp+528h+var_4F8]
0x180019836  mov     rcx, r14
0x180019839  call    ??A?$unordered_map@VHardwareAddress@@VVisibleDock@@V?$hash@VHardwareAddress@@@std@@U?$equal_to@VHardwareAddress@@@4@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@4@@tr1@std@@QEAAAEAVVisibleDock@@AEBVHardwareAddress@@@Z; std::tr1::unordered_map<HardwareAddress,VisibleDock,std::hash<HardwareAddress>,std::equal_to<HardwareAddress>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>::operator[](HardwareAddress const &)
0x18001983e  lea     rcx, [rax+8]
0x180019842  lea     edx, [rsi+1Ch]
0x180019845  mov     [rsp+528h+var_508], rcx
0x18001984a  mov     r9, rdi
0x18001984d  lea     r8, WPP_29db95f43f0434e41d7a9cbe58adf31d_Traceguids
0x180019854  mov     rcx, cs:WPP_GLOBAL_Control
0x18001985b  mov     rcx, [rcx+10h]
0x18001985f  call    WPP_SF_qS
0x180019864  nop
0x180019865  lea     rcx, [rsp+528h+var_4C8]; this
0x18001986a  call    ??1VisibleDock@@QEAA@XZ; VisibleDock::~VisibleDock(void)
0x18001986f  mov     al, 1
0x180019871  jmp     short loc_1800198D1
0x180019873  mov     rax, cs:WPP_GLOBAL_Control
0x18001987a  cmp     rax, r12
0x18001987d  jz      short loc_1800198C1
0x18001987f  cmp     byte ptr [rax+19h], 3
0x180019883  jb      short loc_1800198C1
0x180019885  test    byte ptr [rax+1Ch], 1
0x180019889  jz      short loc_1800198C1
0x18001988b  lea     rdx, [rsp+528h+var_4F8]
0x180019890  mov     rcx, r14
0x180019893  call    ??A?$unordered_map@VHardwareAddress@@VVisibleDock@@V?$hash@VHardwareAddress@@@std@@U?$equal_to@VHardwareAddress@@@4@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@4@@tr1@std@@QEAAAEAVVisibleDock@@AEBVHardwareAddress@@@Z; std::tr1::unordered_map<HardwareAddress,VisibleDock,std::hash<HardwareAddress>,std::equal_to<HardwareAddress>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>::operator[](HardwareAddress const &)
0x180019898  add     rax, 8
0x18001989c  mov     edx, 1Dh
0x1800198a1  mov     [rsp+528h+var_508], rax
0x1800198a6  mov     r9, rdi
0x1800198a9  lea     r8, WPP_29db95f43f0434e41d7a9cbe58adf31d_Traceguids
0x1800198b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800198b7  mov     rcx, [rcx+10h]
0x1800198bb  call    WPP_SF_qS
0x1800198c0  nop
0x1800198c1  lea     rcx, [rsp+528h+var_4C8]; this
0x1800198c6  call    ??1VisibleDock@@QEAA@XZ; VisibleDock::~VisibleDock(void)
0x1800198cb  xor     al, al
0x1800198cd  jmp     short loc_1800198D1
0x1800198cf  xor     al, al
0x1800198d1  mov     rcx, [rsp+528h+var_38]
0x1800198d9  xor     rcx, rsp; StackCookie
0x1800198dc  call    __security_check_cookie
0x1800198e1  mov     rbx, [rsp+528h+arg_10]
0x1800198e9  add     rsp, 500h
0x1800198f0  pop     r14
0x1800198f2  pop     r13
0x1800198f4  pop     r12
0x1800198f6  pop     rdi
0x1800198f7  pop     rsi
0x1800198f8  retn
```
