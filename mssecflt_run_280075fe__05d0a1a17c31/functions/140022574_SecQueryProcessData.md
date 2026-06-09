# SecQueryProcessData

- ea: `0x140022574`
- end: `0x140022aa1`
- name: `SecQueryProcessData`
- size: `1325`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x140021ca0`

## callees

- `0x1400067a4`
- `0x140006b6c`
- `0x140011650`
- `0x140011700`
- `0x1400119c0`
- `0x1400222d0`
- `0x140022574`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x140022655`
- `ntoskrnl!RtlLengthSid` at `0x140022655`

## pseudocode

```c
__int64 __fastcall SecQueryProcessData(__int64 a1, unsigned __int64 a2)
{
  __int64 v3; // rcx
  int ProcessContextByStartkey; // eax
  struct _SLIST_ENTRY *v7; // rcx
  unsigned int v8; // edi
  unsigned int v9; // edx
  unsigned int v10; // edi
  unsigned int v11; // edx
  struct _SLIST_ENTRY *Next; // rax
  unsigned int v13; // eax
  unsigned int v14; // edi
  unsigned int v15; // ebx
  PSID *v16; // rax
  ULONG v17; // eax
  ULONG v18; // r15d
  unsigned int v19; // eax
  __int64 v20; // rax
  int *v21; // rsi
  char *v22; // rbx
  PSLIST_ENTRY v23; // rcx
  PSLIST_ENTRY v24; // rcx
  PSLIST_ENTRY v25; // rcx
  struct _SLIST_ENTRY *v26; // rax
  PSLIST_ENTRY v27; // rdx
  PSLIST_ENTRY v28; // rcx
  PSLIST_ENTRY v29; // rcx
  int v30; // ebx
  PSLIST_ENTRY ListEntry; // [rsp+20h] [rbp-10h] BYREF

  v3 = *(_QWORD *)(a1 + 16);
  ListEntry = 0;
  if ( !v3 )
    return 3221225485LL;
  ProcessContextByStartkey = SecGetProcessContextByStartkey(v3, &ListEntry);
  v7 = ListEntry;
  v8 = ProcessContextByStartkey;
  if ( ProcessContextByStartkey >= 0 )
  {
    v9 = *((unsigned __int16 *)&ListEntry[9].Next + 5) + 536;
    v10 = v9 + WORD1(ListEntry[5].Next);
    if ( v10 < v9 )
      goto LABEL_44;
    v11 = v10 + WORD1(ListEntry[8].Next);
    if ( v11 < v10 )
      goto LABEL_44;
    Next = ListEntry[14].Next;
    if ( Next )
    {
      v13 = v11 + WORD1(Next->Next);
      if ( v13 < v11 )
        goto LABEL_44;
      v11 = v13;
    }
    v14 = v11 + *((unsigned __int16 *)&ListEntry[11].Next + 5);
    if ( v14 < v11 )
      goto LABEL_44;
    v15 = v14 + WORD1(ListEntry[43].Next);
    if ( v15 < v14 )
      goto LABEL_44;
    v16 = (PSID *)*((_QWORD *)&ListEntry[18].Next + 1);
    if ( v16 )
    {
      v17 = RtlLengthSid(*v16);
      v7 = ListEntry;
      v18 = v17;
      v19 = v15 + v17;
      if ( v19 < v15 )
        goto LABEL_44;
      v15 = v19;
    }
    else
    {
      v18 = 0;
    }
    v20 = *(unsigned int *)(a2 + 8);
    if ( (unsigned int)v20 < v15 )
    {
      v8 = -1073741801;
      *(_DWORD *)(a2 + 16) = v15;
      goto LABEL_45;
    }
    v21 = (int *)(a2 + 168);
    if ( a2 + 168 >= a2 )
    {
      memset(v21, 0, v20 - 168);
      *(_DWORD *)(a2 + 172) = ListEntry[2].Next;
      *(_QWORD *)(a2 + 176) = *((_QWORD *)&ListEntry[2].Next + 1);
      *(_QWORD *)(a2 + 184) = ListEntry[3].Next;
      *(_DWORD *)(a2 + 192) = *((_DWORD *)&ListEntry[3].Next + 2);
      *(_QWORD *)(a2 + 200) = ListEntry[4].Next;
      *(_QWORD *)(a2 + 208) = *((_QWORD *)&ListEntry[4].Next + 1);
      *(_DWORD *)(a2 + 216) = *((_DWORD *)&ListEntry[6].Next + 2);
      *(_QWORD *)(a2 + 224) = ListEntry[7].Next;
      *(_QWORD *)(a2 + 232) = *((_QWORD *)&ListEntry[7].Next + 1);
      *(_BYTE *)(a2 + 408) = ListEntry[36].Next;
      *(_DWORD *)(a2 + 412) = *((_DWORD *)&ListEntry[16].Next + 2);
      *(_DWORD *)(a2 + 416) = HIDWORD(ListEntry[17].Next);
      *(_BYTE *)(a2 + 420) = *((_DWORD *)&ListEntry[17].Next + 2) != 0;
      *(_QWORD *)(a2 + 424) = ListEntry[18].Next;
      *(_BYTE *)(a2 + 421) = 0;
      *(_QWORD *)(a2 + 432) = *((_QWORD *)&ListEntry[36].Next + 1);
      *(_DWORD *)(a2 + 440) = ListEntry[37].Next;
      *(_BYTE *)(a2 + 444) = BYTE4(ListEntry[37].Next);
      *(_DWORD *)(a2 + 504) = *((_DWORD *)&ListEntry[38].Next + 2);
      *(_QWORD *)(a2 + 480) = *((_QWORD *)&ListEntry[35].Next + 1);
      *(_DWORD *)(a2 + 488) = ListEntry[39].Next;
      *(_QWORD *)(a2 + 496) = *((_QWORD *)&ListEntry[39].Next + 1);
      *(_DWORD *)(a2 + 508) = ListEntry[40].Next;
      *(_DWORD *)(a2 + 512) = HIDWORD(ListEntry[40].Next);
      *(_DWORD *)(a2 + 516) = ListEntry[42].Next;
      *(_DWORD *)(a2 + 520) = HIDWORD(ListEntry[42].Next);
      *(_DWORD *)(a2 + 524) = *((_DWORD *)&ListEntry[42].Next + 2);
      if ( *(_BYTE *)(a1 + 24) )
        SecObtainFileHashForProcess(ListEntry, a2 + 260);
      else
        memset((void *)(a2 + 260), 0, 0x94u);
      v22 = (char *)(a2 + 532);
      if ( *((_WORD *)&ListEntry[9].Next + 4) )
      {
        *(_DWORD *)(a2 + 240) = 364;
        memmove((void *)(a2 + 532), ListEntry[10].Next, *((unsigned __int16 *)&ListEntry[9].Next + 5));
        v23 = ListEntry;
        v22 += *((unsigned __int16 *)&ListEntry[9].Next + 5);
      }
      else
      {
        *(_DWORD *)(a2 + 240) = 0;
        v23 = ListEntry;
      }
      if ( LOWORD(v23[5].Next) )
      {
        *(_DWORD *)(a2 + 244) = (_DWORD)v22 - (_DWORD)v21;
        memmove(v22, *((const void **)&ListEntry[5].Next + 1), WORD1(ListEntry[5].Next));
        v24 = ListEntry;
        v22 += WORD1(ListEntry[5].Next);
      }
      else
      {
        *(_DWORD *)(a2 + 244) = 0;
        v24 = ListEntry;
      }
      if ( LOWORD(v24[8].Next) )
      {
        *(_DWORD *)(a2 + 248) = (_DWORD)v22 - (_DWORD)v21;
        memmove(v22, *((const void **)&ListEntry[8].Next + 1), WORD1(ListEntry[8].Next));
        v25 = ListEntry;
        v22 += WORD1(ListEntry[8].Next);
      }
      else
      {
        *(_DWORD *)(a2 + 248) = 0;
        v25 = ListEntry;
      }
      v26 = v25[14].Next;
      if ( v26 && LOWORD(v26->Next) )
      {
        *(_DWORD *)(a2 + 252) = (_DWORD)v22 - (a2 + 168);
        memmove(v22, *((const void **)&ListEntry[14].Next->Next + 1), WORD1(ListEntry[14].Next->Next));
        v27 = ListEntry;
        v22 += WORD1(ListEntry[14].Next->Next);
      }
      else
      {
        *(_DWORD *)(a2 + 252) = 0;
        v27 = ListEntry;
      }
      if ( *((_WORD *)&v27[11].Next + 4) )
      {
        *(_DWORD *)(a2 + 472) = (_DWORD)v22 - (_DWORD)v21;
        memmove(v22, ListEntry[12].Next, *((unsigned __int16 *)&ListEntry[11].Next + 5));
        v28 = ListEntry;
        v22 += *((unsigned __int16 *)&ListEntry[11].Next + 5);
      }
      else
      {
        *(_DWORD *)(a2 + 472) = 0;
        v28 = ListEntry;
      }
      if ( LOWORD(v28[43].Next) )
      {
        *(_DWORD *)(a2 + 528) = (_DWORD)v22 - (_DWORD)v21;
        memmove(v22, *((const void **)&ListEntry[43].Next + 1), WORD1(ListEntry[43].Next));
        v29 = ListEntry;
        v22 += WORD1(ListEntry[43].Next);
      }
      else
      {
        *(_DWORD *)(a2 + 528) = 0;
        v29 = ListEntry;
      }
      *(struct _SLIST_ENTRY *)(a2 + 448) = *(PSLIST_ENTRY)((char *)v29 + 200);
      *(_QWORD *)(a2 + 464) = *((_QWORD *)&v29[13].Next + 1);
      if ( v18 )
      {
        *(_DWORD *)(a2 + 256) = (_DWORD)v22 - (a2 + 168);
        memmove(v22, **((const void ***)&ListEntry[18].Next + 1), v18);
        LODWORD(v22) = v18 + (_DWORD)v22;
      }
      else
      {
        *(_DWORD *)(a2 + 256) = 0;
      }
      v30 = (_DWORD)v22 - (_DWORD)v21;
      v8 = 0;
      *v21 = v30;
      v7 = ListEntry;
      *(_DWORD *)(a2 + 16) = v30;
      goto LABEL_45;
    }
LABEL_44:
    v8 = -1073741675;
  }
LABEL_45:
  if ( v7 )
    SecReleaseProcessContext(v7);
  return v8;
}

```

## disassembly

```asm
0x140022574  mov     [rsp-38h+arg_10], rbx
0x140022579  push    rbp
0x14002257a  push    rsi
0x14002257b  push    rdi
0x14002257c  push    r12
0x14002257e  push    r13
0x140022580  push    r14
0x140022582  push    r15
0x140022584  mov     rbp, rsp
0x140022587  sub     rsp, 30h
0x14002258b  mov     rax, cs:__security_cookie
0x140022592  xor     rax, rsp
0x140022595  mov     [rbp+var_8], rax
0x140022599  xor     r12d, r12d
0x14002259c  mov     r13, rcx
0x14002259f  mov     rcx, [rcx+10h]
0x1400225a3  mov     r14, rdx
0x1400225a6  mov     [rbp+ListEntry], r12
0x1400225aa  test    rcx, rcx
0x1400225ad  jnz     short loc_1400225B9
0x1400225af  mov     eax, 0C000000Dh
0x1400225b4  jmp     loc_140022A7C
0x1400225b9  lea     rdx, [rbp+ListEntry]
0x1400225bd  call    SecGetProcessContextByStartkey
0x1400225c2  mov     rcx, [rbp+ListEntry]; ListEntry
0x1400225c6  mov     edi, eax
0x1400225c8  test    eax, eax
0x1400225ca  js      loc_140022A70
0x1400225d0  movzx   edx, word ptr [rcx+9Ah]
0x1400225d7  add     edx, 218h
0x1400225dd  cmp     edx, 218h
0x1400225e3  jb      loc_140022A6B
0x1400225e9  movzx   edi, word ptr [rcx+52h]
0x1400225ed  add     edi, edx
0x1400225ef  cmp     edi, edx
0x1400225f1  jb      loc_140022A6B
0x1400225f7  movzx   edx, word ptr [rcx+82h]
0x1400225fe  add     edx, edi
0x140022600  cmp     edx, edi
0x140022602  jb      loc_140022A6B
0x140022608  mov     rax, [rcx+0E0h]
0x14002260f  test    rax, rax
0x140022612  jz      short loc_140022624
0x140022614  movzx   eax, word ptr [rax+2]
0x140022618  add     eax, edx
0x14002261a  cmp     eax, edx
0x14002261c  jb      loc_140022A6B
0x140022622  mov     edx, eax
0x140022624  movzx   edi, word ptr [rcx+0BAh]
0x14002262b  add     edi, edx
0x14002262d  cmp     edi, edx
0x14002262f  jb      loc_140022A6B
0x140022635  movzx   ebx, word ptr [rcx+2B2h]
0x14002263c  add     ebx, edi
0x14002263e  cmp     ebx, edi
0x140022640  jb      loc_140022A6B
0x140022646  mov     rax, [rcx+128h]
0x14002264d  test    rax, rax
0x140022650  jz      short loc_140022676
0x140022652  mov     rcx, [rax]; Sid
0x140022655  call    cs:__imp_RtlLengthSid
0x14002265c  nop     dword ptr [rax+rax+00h]
0x140022661  mov     rcx, [rbp+ListEntry]
0x140022665  mov     r15d, eax
0x140022668  add     eax, ebx
0x14002266a  cmp     eax, ebx
0x14002266c  jb      loc_140022A6B
0x140022672  mov     ebx, eax
0x140022674  jmp     short loc_140022679
0x140022676  mov     r15d, r12d
0x140022679  mov     eax, [r14+8]
0x14002267d  cmp     eax, ebx
0x14002267f  jnb     short loc_14002268F
0x140022681  mov     edi, 0C0000017h
0x140022686  mov     [r14+10h], ebx
0x14002268a  jmp     loc_140022A70
0x14002268f  lea     rsi, [r14+0A8h]
0x140022696  cmp     rsi, r14
0x140022699  jb      loc_140022A6B
0x14002269f  lea     rcx, [rax-0A8h]
0x1400226a6  mov     rdi, rsi
0x1400226a9  xor     eax, eax
0x1400226ab  rep stosb
0x1400226ad  mov     rax, [rbp+ListEntry]
0x1400226b1  mov     ecx, [rax+20h]
0x1400226b4  mov     [rsi+4], ecx
0x1400226b7  mov     rax, [rbp+ListEntry]
0x1400226bb  mov     rcx, [rax+28h]
0x1400226bf  mov     [rsi+8], rcx
0x1400226c3  mov     rax, [rbp+ListEntry]
0x1400226c7  mov     rcx, [rax+30h]
0x1400226cb  mov     [rsi+10h], rcx
0x1400226cf  mov     rax, [rbp+ListEntry]
0x1400226d3  mov     ecx, [rax+38h]
0x1400226d6  mov     [rsi+18h], ecx
0x1400226d9  mov     rax, [rbp+ListEntry]
0x1400226dd  mov     rcx, [rax+40h]
0x1400226e1  mov     [rsi+20h], rcx
0x1400226e5  mov     rax, [rbp+ListEntry]
0x1400226e9  mov     rcx, [rax+48h]
0x1400226ed  mov     [rsi+28h], rcx
0x1400226f1  mov     rax, [rbp+ListEntry]
0x1400226f5  mov     ecx, [rax+68h]
0x1400226f8  mov     [rsi+30h], ecx
0x1400226fb  mov     rax, [rbp+ListEntry]
0x1400226ff  mov     rcx, [rax+70h]
0x140022703  mov     [rsi+38h], rcx
0x140022707  mov     rax, [rbp+ListEntry]
0x14002270b  mov     rcx, [rax+78h]
0x14002270f  mov     [rsi+40h], rcx
0x140022713  mov     rax, [rbp+ListEntry]
0x140022717  mov     cl, [rax+240h]
0x14002271d  mov     [rsi+0F0h], cl
0x140022723  mov     rax, [rbp+ListEntry]
0x140022727  mov     ecx, [rax+108h]
0x14002272d  mov     [rsi+0F4h], ecx
0x140022733  mov     rax, [rbp+ListEntry]
0x140022737  mov     ecx, [rax+114h]
0x14002273d  mov     [rsi+0F8h], ecx
0x140022743  mov     rax, [rbp+ListEntry]
0x140022747  cmp     [rax+118h], r12d
0x14002274e  setnz   al
0x140022751  mov     [rsi+0FCh], al
0x140022757  mov     rax, [rbp+ListEntry]
0x14002275b  mov     rcx, [rax+120h]
0x140022762  mov     [rsi+100h], rcx
0x140022769  mov     [rsi+0FDh], r12b
0x140022770  mov     rax, [rbp+ListEntry]
0x140022774  mov     rcx, [rax+248h]
0x14002277b  mov     [rsi+108h], rcx
0x140022782  mov     rax, [rbp+ListEntry]
0x140022786  mov     ecx, [rax+250h]
0x14002278c  mov     [rsi+110h], ecx
0x140022792  mov     rax, [rbp+ListEntry]
0x140022796  mov     cl, [rax+254h]
0x14002279c  mov     [rsi+114h], cl
0x1400227a2  mov     rax, [rbp+ListEntry]
0x1400227a6  mov     ecx, [rax+268h]
0x1400227ac  mov     [rsi+150h], ecx
0x1400227b2  mov     rax, [rbp+ListEntry]
0x1400227b6  mov     rcx, [rax+238h]
0x1400227bd  mov     [rsi+138h], rcx
0x1400227c4  mov     rax, [rbp+ListEntry]
0x1400227c8  mov     ecx, [rax+270h]
0x1400227ce  mov     [rsi+140h], ecx
0x1400227d4  mov     rax, [rbp+ListEntry]
0x1400227d8  mov     rcx, [rax+278h]
0x1400227df  mov     [rsi+148h], rcx
0x1400227e6  mov     rax, [rbp+ListEntry]
0x1400227ea  mov     ecx, [rax+280h]
0x1400227f0  mov     [rsi+154h], ecx
0x1400227f6  mov     rax, [rbp+ListEntry]
0x1400227fa  mov     ecx, [rax+284h]
0x140022800  mov     [rsi+158h], ecx
0x140022806  mov     rax, [rbp+ListEntry]
0x14002280a  mov     ecx, [rax+2A0h]
0x140022810  mov     [rsi+15Ch], ecx
0x140022816  mov     rax, [rbp+ListEntry]
0x14002281a  mov     ecx, [rax+2A4h]
0x140022820  mov     [rsi+160h], ecx
0x140022826  mov     rax, [rbp+ListEntry]
0x14002282a  mov     ecx, [rax+2A8h]
0x140022830  mov     [rsi+164h], ecx
0x140022836  lea     rcx, [rsi+5Ch]; void *
0x14002283a  cmp     [r13+18h], r12b
0x14002283e  jz      short loc_14002284E
0x140022840  mov     rdx, rcx
0x140022843  mov     rcx, [rbp+ListEntry]
0x140022847  call    SecObtainFileHashForProcess
0x14002284c  jmp     short loc_14002285B
0x14002284e  xor     edx, edx; Val
0x140022850  mov     r8d, 94h; Size
0x140022856  call    memset
0x14002285b  mov     rax, [rbp+ListEntry]
0x14002285f  lea     rbx, [rsi+16Ch]
0x140022866  cmp     r12w, [rax+98h]
0x14002286e  jz      short loc_1400228A2
0x140022870  mov     eax, ebx
0x140022872  mov     rcx, rbx; void *
0x140022875  sub     eax, esi
0x140022877  mov     [rsi+48h], eax
0x14002287a  mov     rdx, [rbp+ListEntry]
0x14002287e  movzx   r8d, word ptr [rdx+9Ah]; Size
0x140022886  mov     rdx, [rdx+0A0h]; Src
0x14002288d  call    memmove
0x140022892  mov     rcx, [rbp+ListEntry]
0x140022896  movzx   eax, word ptr [rcx+9Ah]
0x14002289d  add     rbx, rax
0x1400228a0  jmp     short loc_1400228AA
0x1400228a2  mov     [rsi+48h], r12d
0x1400228a6  mov     rcx, [rbp+ListEntry]
0x1400228aa  cmp     r12w, [rcx+50h]
0x1400228af  jz      short loc_1400228DA
0x1400228b1  mov     eax, ebx
0x1400228b3  mov     rcx, rbx; void *
0x1400228b6  sub     eax, esi
0x1400228b8  mov     [rsi+4Ch], eax
0x1400228bb  mov     rdx, [rbp+ListEntry]
0x1400228bf  movzx   r8d, word ptr [rdx+52h]; Size
0x1400228c4  mov     rdx, [rdx+58h]; Src
0x1400228c8  call    memmove
0x1400228cd  mov     rcx, [rbp+ListEntry]
0x1400228d1  movzx   eax, word ptr [rcx+52h]
0x1400228d5  add     rbx, rax
0x1400228d8  jmp     short loc_1400228E2
0x1400228da  mov     [rsi+4Ch], r12d
0x1400228de  mov     rcx, [rbp+ListEntry]
0x1400228e2  cmp     r12w, [rcx+80h]
0x1400228ea  jz      short loc_14002291E
0x1400228ec  mov     eax, ebx
0x1400228ee  mov     rcx, rbx; void *
0x1400228f1  sub     eax, esi
0x1400228f3  mov     [rsi+50h], eax
0x1400228f6  mov     rdx, [rbp+ListEntry]
0x1400228fa  movzx   r8d, word ptr [rdx+82h]; Size
0x140022902  mov     rdx, [rdx+88h]; Src
0x140022909  call    memmove
0x14002290e  mov     rcx, [rbp+ListEntry]
0x140022912  movzx   eax, word ptr [rcx+82h]
0x140022919  add     rbx, rax
0x14002291c  jmp     short loc_140022926
0x14002291e  mov     [rsi+50h], r12d
0x140022922  mov     rcx, [rbp+ListEntry]
0x140022926  mov     rax, [rcx+0E0h]
0x14002292d  test    rax, rax
0x140022930  jz      short loc_14002296F
0x140022932  cmp     r12w, [rax]
0x140022936  jz      short loc_14002296F
0x140022938  mov     eax, ebx
0x14002293a  mov     rcx, rbx; void *
0x14002293d  sub     eax, esi
0x14002293f  mov     [rsi+54h], eax
0x140022942  mov     rax, [rbp+ListEntry]
0x140022946  mov     rdx, [rax+0E0h]
0x14002294d  movzx   r8d, word ptr [rdx+2]; Size
0x140022952  mov     rdx, [rdx+8]; Src
0x140022956  call    memmove
0x14002295b  mov     rdx, [rbp+ListEntry]
0x14002295f  mov     rax, [rdx+0E0h]
0x140022966  movzx   ecx, word ptr [rax+2]
0x14002296a  add     rbx, rcx
0x14002296d  jmp     short loc_140022977
0x14002296f  mov     [rsi+54h], r12d
0x140022973  mov     rdx, [rbp+ListEntry]
0x140022977  cmp     r12w, [rdx+0B8h]
0x14002297f  jz      short loc_1400229B6
0x140022981  mov     eax, ebx
0x140022983  mov     rcx, rbx; void *
0x140022986  sub     eax, esi
0x140022988  mov     [rsi+130h], eax
0x14002298e  mov     rdx, [rbp+ListEntry]
0x140022992  movzx   r8d, word ptr [rdx+0BAh]; Size
0x14002299a  mov     rdx, [rdx+0C0h]; Src
0x1400229a1  call    memmove
0x1400229a6  mov     rcx, [rbp+ListEntry]
0x1400229aa  movzx   eax, word ptr [rcx+0BAh]
0x1400229b1  add     rbx, rax
0x1400229b4  jmp     short loc_1400229C1
0x1400229b6  mov     [rsi+130h], r12d
0x1400229bd  mov     rcx, [rbp+ListEntry]
0x1400229c1  cmp     r12w, [rcx+2B0h]
0x1400229c9  jz      short loc_140022A00
0x1400229cb  mov     eax, ebx
0x1400229cd  mov     rcx, rbx; void *
0x1400229d0  sub     eax, esi
0x1400229d2  mov     [rsi+168h], eax
0x1400229d8  mov     rdx, [rbp+ListEntry]
0x1400229dc  movzx   r8d, word ptr [rdx+2B2h]; Size
0x1400229e4  mov     rdx, [rdx+2B8h]; Src
0x1400229eb  call    memmove
0x1400229f0  mov     rcx, [rbp+ListEntry]
0x1400229f4  movzx   eax, word ptr [rcx+2B2h]
0x1400229fb  add     rbx, rax
0x1400229fe  jmp     short loc_140022A0B
0x140022a00  mov     [rsi+168h], r12d
0x140022a07  mov     rcx, [rbp+ListEntry]
0x140022a0b  movups  xmm0, xmmword ptr [rcx+0C8h]
0x140022a12  movups  xmmword ptr [rsi+118h], xmm0
0x140022a19  movsd   xmm1, qword ptr [rcx+0D8h]
0x140022a21  movsd   qword ptr [rsi+128h], xmm1
0x140022a29  test    r15d, r15d
0x140022a2c  jz      short loc_140022A56
0x140022a2e  mov     eax, ebx
0x140022a30  mov     r8d, r15d; Size
0x140022a33  sub     eax, esi
0x140022a35  mov     edi, r15d
0x140022a38  mov     [rsi+58h], eax
0x140022a3b  mov     rcx, rbx; void *
0x140022a3e  mov     rax, [rbp+ListEntry]
0x140022a42  mov     rdx, [rax+128h]
0x140022a49  mov     rdx, [rdx]; Src
0x140022a4c  call    memmove
0x140022a51  add     rbx, rdi
0x140022a54  jmp     short loc_140022A5A
0x140022a56  mov     [rsi+58h], r12d
0x140022a5a  sub     ebx, esi
0x140022a5c  mov     edi, r12d
0x140022a5f  mov     [rsi], ebx
0x140022a61  mov     rcx, [rbp+ListEntry]
0x140022a65  mov     [r14+10h], ebx
  ... truncated ...
```
