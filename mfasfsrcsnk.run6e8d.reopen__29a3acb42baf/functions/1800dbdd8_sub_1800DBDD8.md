# sub_1800DBDD8

- ea: `0x1800dbdd8`
- end: `0x1800dc5f3`
- name: `sub_1800DBDD8`
- size: `2075`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1800d8210`

## callees

- `0x180001870`
- `0x180005880`
- `0x18000a580`
- `0x180024f38`
- `0x18002d560`
- `0x18003d740`
- `0x18004f28c`
- `0x18004f390`
- `0x1800520c4`
- `0x18007fdd0`
- `0x1800da3bc`
- `0x1800dbdd8`
- `0x18013501c`
- `0x18013e2e0`

## import_xrefs

- `MFPlat!MFWrapMediaType` at `0x1800dc491`
- `MFPlat!MFWrapMediaType` at `0x1800dc491`
- `MFPlat!MFCreateMediaType` at `0x1800dc039`
- `MFPlat!MFCreateMediaType` at `0x1800dc039`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dbee6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc055`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc120`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc1e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc287`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc350`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc401`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc4d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dbee6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc055`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc120`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc1e1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc287`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc350`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc401`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800dc4d7`

## pseudocode

```c
__int64 __fastcall sub_1800DBDD8(__int64 a1, __int64 a2)
{
  HRESULT v3; // ebx
  __int64 v4; // rdx
  __int64 (__fastcall ***v5)(); // rcx
  __int64 v6; // rax
  __int64 v7; // rax
  int v8; // ecx
  int v9; // edx
  int v10; // ecx
  char v11; // al
  char v12; // al
  BOOL v13; // eax
  __int64 v14; // rdx
  __int64 (__fastcall ***v15)(); // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 (__fastcall ***v20)(); // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 (__fastcall ***v24)(); // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 (__fastcall ***v28)(); // rcx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // r14
  __int64 v32; // rdx
  __int64 (__fastcall ***v33)(); // rcx
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rdx
  __int64 (__fastcall ***v37)(); // rcx
  __int64 v38; // rax
  __int64 v39; // rax
  IMFMediaType *v40; // rax
  __int64 v41; // rdx
  __int64 (__fastcall ***v42)(); // rcx
  __int64 v43; // rax
  __int64 v44; // rax
  IMFMediaType *v45; // rcx
  __int64 v46; // rdx
  _BYTE v48[4]; // [rsp+30h] [rbp-39h] BYREF
  int v49; // [rsp+34h] [rbp-35h] BYREF
  __int64 v50; // [rsp+38h] [rbp-31h] BYREF
  IMFMediaType *ppMFType; // [rsp+40h] [rbp-29h] BYREF
  unsigned __int8 v52; // [rsp+48h] [rbp-21h] BYREF
  unsigned __int8 v53; // [rsp+49h] [rbp-20h]
  IMFMediaType *ppWrap; // [rsp+50h] [rbp-19h] BYREF
  int v55; // [rsp+58h] [rbp-11h] BYREF
  GUID SubType; // [rsp+60h] [rbp-9h] BYREF
  GUID MajorType; // [rsp+70h] [rbp+7h] BYREF

  v3 = 0;
  v55 = 0;
  if ( *(_DWORD *)(a1 + 1256)
    && (*(int (__fastcall **)(__int64, __int64 *, unsigned __int8 *, __int64, int *))(*(_QWORD *)a2 + 120LL))(
         a2,
         qword_18014DBA8,
         &v52,
         2,
         &v55) >= 0
    && v55 == 2 )
  {
    sub_18000A580(v48, "CASFBytewiseMediaStream::QueueFormatChangedEventIfNeeded", 1273);
    if ( (unsigned __int8)byte_1801692CB >= 0x20u )
      sub_1800520C4(*((_QWORD *)RequestContext + 17), 101, &stru_180158D48, a1);
    if ( !v52 || !v53 )
      goto LABEL_123;
    LODWORD(ppMFType) = 0;
    v49 = 0;
    if ( !*(_QWORD *)(a1 + 1248) )
    {
      v3 = sub_18002D560(a1);
      if ( v3 < 0 )
      {
        v5 = (__int64 (__fastcall ***)())qword_180169350;
        if ( !qword_180169350 )
        {
          v6 = MFGetCallStackTracingWeakReference(0, v4);
          qword_180169350 = v6;
          if ( v6 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
          {
            v5 = (__int64 (__fastcall ***)())qword_180169350;
          }
          else
          {
            v5 = &off_1801683B0;
            qword_180169350 = (__int64)&off_1801683B0;
          }
        }
        if ( *((_BYTE *)v5 + 8) )
        {
          v7 = sub_180001870(v5);
          if ( *(_DWORD *)(v7 + 1996) != v3 )
            sub_18007FDD0(v7, "CASFBytewiseMediaStream::QueueFormatChangedEventIfNeeded", 1290, (unsigned int)v3);
        }
        if ( byte_1801692C8 )
          sub_18004F390(*((_QWORD *)RequestContext + 2), 102, &stru_180158D48, a1, v3);
        goto LABEL_123;
      }
    }
    v3 = sub_18004F28C(*(_QWORD *)(a1 + 1248), qword_18014EBD0, &ppMFType, &v49);
    if ( v3 >= 0 )
    {
      v8 = (int)ppMFType;
      v9 = v49;
    }
    else
    {
      v8 = 1;
      v9 = 1;
      v3 = 0;
    }
    if ( v8 != v52 || (v10 = 0, v9 != v53) )
      v10 = 1;
    v11 = *(_BYTE *)(a1 + 1260);
    v13 = 1;
    if ( !v11 || v52 == v11 )
    {
      v12 = *(_BYTE *)(a1 + 1261);
      if ( !v12 || v53 == v12 )
        v13 = 0;
    }
    if ( !v10 && !v13 )
      goto LABEL_123;
    if ( (unsigned __int8)byte_1801692CB >= 8u )
      sub_1800520C4(*((_QWORD *)RequestContext + 17), 103, &stru_180158D48, a1);
    ppMFType = 0;
    v50 = 0;
    ppWrap = 0;
    v49 = 0;
    v3 = MFCreateMediaType(&ppMFType);
    if ( v3 < 0 )
    {
      v15 = (__int64 (__fastcall ***)())qword_180169350;
      if ( !qword_180169350 )
      {
        v16 = MFGetCallStackTracingWeakReference(0, v14);
        qword_180169350 = v16;
        if ( v16 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        {
          v15 = (__int64 (__fastcall ***)())qword_180169350;
        }
        else
        {
          v15 = &off_1801683B0;
          qword_180169350 = (__int64)&off_1801683B0;
        }
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        v17 = sub_180001870(v15);
        if ( *(_DWORD *)(v17 + 1996) != v3 )
          sub_18007FDD0(v17, "CASFBytewiseMediaStream::QueueFormatChangedEventIfNeeded", 1329, (unsigned int)v3);
      }
      if ( !byte_1801692C8 )
        goto LABEL_122;
      v18 = 104;
      goto LABEL_47;
    }
    v3 = (*(__int64 (__fastcall **)(_QWORD, IMFMediaType *))(**(_QWORD **)(a1 + 1248) + 256LL))(
           *(_QWORD *)(a1 + 1248),
           ppMFType);
    if ( v3 < 0 )
    {
      v20 = (__int64 (__fastcall ***)())qword_180169350;
      if ( !qword_180169350 )
      {
        v21 = MFGetCallStackTracingWeakReference(0, v19);
        qword_180169350 = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = (__int64 (__fastcall ***)())qword_180169350;
        }
        else
        {
          v20 = &off_1801683B0;
          qword_180169350 = (__int64)&off_1801683B0;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v22 = sub_180001870(v20);
        if ( *(_DWORD *)(v22 + 1996) != v3 )
          sub_18007FDD0(v22, "CASFBytewiseMediaStream::QueueFormatChangedEventIfNeeded", 1331, (unsigned int)v3);
      }
      if ( !byte_1801692C8 )
        goto LABEL_122;
      v18 = 105;
      goto LABEL_47;
    }
    v3 = ((__int64 (__fastcall *)(IMFMediaType *, __int64 *, unsigned __int64))ppMFType->lpVtbl->SetUINT64)(
           ppMFType,
           qword_18014EBD0,
           v53 | ((unsigned __int64)v52 << 32));
    if ( v3 < 0 )
    {
      v24 = (__int64 (__fastcall ***)())qword_180169350;
      if ( !qword_180169350 )
      {
        v25 = MFGetCallStackTracingWeakReference(0, v23);
        qword_180169350 = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v24 = (__int64 (__fastcall ***)())qword_180169350;
        }
        else
        {
          v24 = &off_1801683B0;
          qword_180169350 = (__int64)&off_1801683B0;
        }
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v26 = sub_180001870(v24);
        if ( *(_DWORD *)(v26 + 1996) != v3 )
          sub_18007FDD0(v26, "CASFBytewiseMediaStream::QueueFormatChangedEventIfNeeded", 1336, (unsigned int)v3);
      }
      if ( !byte_1801692C8 )
        goto LABEL_122;
      v18 = 106;
      goto LABEL_47;
    }
    v3 = sub_1800DA3BC(a1, &v49, &v50);
    if ( v3 < 0 )
    {
      v28 = (__int64 (__fastcall ***)())qword_180169350;
      if ( !qword_180169350 )
      {
        v29 = MFGetCallStackTracingWeakReference(0, v27);
        qword_180169350 = v29;
        if ( v29 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
        {
          v28 = (__int64 (__fastcall ***)())qword_180169350;
        }
        else
        {
          v28 = &off_1801683B0;
          qword_180169350 = (__int64)&off_1801683B0;
        }
      }
      if ( *((_BYTE *)v28 + 8) )
      {
        v30 = sub_180001870(v28);
        if ( *(_DWORD *)(v30 + 1996) != v3 )
          sub_18007FDD0(v30, "CASFBytewiseMediaStream::QueueFormatChangedEventIfNeeded", 1338, (unsigned int)v3);
      }
      if ( !byte_1801692C8 )
        goto LABEL_122;
      v18 = 107;
      goto LABEL_47;
    }
    if ( v49 )
    {
      v31 = v50;
      SubType = 0;
      MajorType = 0;
      v3 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v50 + 264LL))(v50, &MajorType);
      if ( v3 < 0 )
      {
        v33 = (__int64 (__fastcall ***)())qword_180169350;
        if ( !qword_180169350 )
        {
          v34 = MFGetCallStackTracingWeakReference(0, v32);
          qword_180169350 = v34;
          if ( v34 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
          {
            v33 = (__int64 (__fastcall ***)())qword_180169350;
          }
          else
          {
            v33 = &off_1801683B0;
            qword_180169350 = (__int64)&off_1801683B0;
          }
        }
        if ( *((_BYTE *)v33 + 8) )
        {
          v35 = sub_180001870(v33);
          if ( *(_DWORD *)(v35 + 1996) != v3 )
            sub_18007FDD0(v35, "CASFBytewiseMediaStream::QueueFormatChangedEventIfNeeded", 1347, (unsigned int)v3);
        }
        if ( !byte_1801692C8 )
          goto LABEL_122;
        v18 = 108;
        goto LABEL_47;
      }
      v3 = (*(__int64 (__fastcall **)(__int64, __int64 *, GUID *))(*(_QWORD *)v31 + 80LL))(
             v31,
             qword_18014EAD0,
             &SubType);
      if ( v3 < 0 )
      {
        v37 = (__int64 (__fastcall ***)())qword_180169350;
        if ( !qword_180169350 )
        {
          v38 = MFGetCallStackTracingWeakReference(0, v36);
          qword_180169350 = v38;
          if ( v38 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
          {
            v37 = (__int64 (__fastcall ***)())qword_180169350;
          }
          else
          {
            v37 = &off_1801683B0;
            qword_180169350 = (__int64)&off_1801683B0;
          }
        }
        if ( *((_BYTE *)v37 + 8) )
        {
          v39 = sub_180001870(v37);
          if ( *(_DWORD *)(v39 + 1996) != v3 )
            sub_18007FDD0(v39, "CASFBytewiseMediaStream::QueueFormatChangedEventIfNeeded", 1349, (unsigned int)v3);
        }
        if ( !byte_1801692C8 )
          goto LABEL_122;
        v18 = 109;
        goto LABEL_47;
      }
      MFWrapMediaType(ppMFType, &MajorType, &SubType, &ppWrap);
      v40 = ppWrap;
    }
    else
    {
      v40 = ppMFType;
    }
    v3 = sub_18013501C((int)a1 + 160, 216, (unsigned int)&Buf1, 0, (__int64)v40);
    if ( v3 >= 0 )
    {
      v45 = ppMFType;
      *(_BYTE *)(a1 + 1260) = v52;
      *(_BYTE *)(a1 + 1261) = v53;
      if ( v45 )
      {
        ((void (__fastcall *)(IMFMediaType *))v45->lpVtbl->AddRef)(v45);
        v45 = ppMFType;
      }
      v46 = *(_QWORD *)(a1 + 1248);
      if ( v46 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v46 + 16LL))(*(_QWORD *)(a1 + 1248));
        v45 = ppMFType;
      }
      *(_QWORD *)(a1 + 1248) = v45;
      goto LABEL_122;
    }
    v42 = (__int64 (__fastcall ***)())qword_180169350;
    if ( !qword_180169350 )
    {
      v43 = MFGetCallStackTracingWeakReference(0, v41);
      qword_180169350 = v43;
      if ( v43 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
      {
        v42 = (__int64 (__fastcall ***)())qword_180169350;
      }
      else
      {
        v42 = &off_1801683B0;
        qword_180169350 = (__int64)&off_1801683B0;
      }
    }
    if ( *((_BYTE *)v42 + 8) )
    {
      v44 = sub_180001870(v42);
      if ( *(_DWORD *)(v44 + 1996) != v3 )
        sub_18007FDD0(v44, "CASFBytewiseMediaStream::QueueFormatChangedEventIfNeeded", 1364, (unsigned int)v3);
    }
    if ( !byte_1801692C8 )
    {
LABEL_122:
      sub_180024F38(&ppWrap);
      sub_180024F38(&v50);
      sub_180024F38(&ppMFType);
LABEL_123:
      sub_180005880(v48);
      return (unsigned int)v3;
    }
    v18 = 110;
LABEL_47:
    sub_18004F390(*((_QWORD *)RequestContext + 2), v18, &stru_180158D48, a1, v3);
    goto LABEL_122;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800dbdd8  mov     [rsp-8+arg_10], rbx
0x1800dbddd  push    rbp
0x1800dbdde  push    rsi
0x1800dbddf  push    rdi
0x1800dbde0  push    r12
0x1800dbde2  push    r13
0x1800dbde4  push    r14
0x1800dbde6  push    r15
0x1800dbde8  lea     rbp, [rsp-27h]
0x1800dbded  sub     rsp, 90h
0x1800dbdf4  mov     rax, cs:__security_cookie
0x1800dbdfb  xor     rax, rsp
0x1800dbdfe  mov     [rbp+57h+var_40], rax
0x1800dbe02  xor     r15d, r15d
0x1800dbe05  mov     r10, rdx
0x1800dbe08  mov     rdi, rcx
0x1800dbe0b  mov     ebx, r15d
0x1800dbe0e  mov     [rbp+57h+var_68], r15d
0x1800dbe12  cmp     [rcx+4E8h], r15d
0x1800dbe19  jz      loc_1800DC5CA
0x1800dbe1f  mov     rax, [rdx]
0x1800dbe22  lea     rcx, [rbp+57h+var_68]
0x1800dbe26  mov     [rsp+0C0h+var_A0], rcx
0x1800dbe2b  lea     r9d, [r15+2]
0x1800dbe2f  lea     r8, [rbp+57h+var_78]
0x1800dbe33  mov     rcx, r10
0x1800dbe36  lea     rdx, qword_18014DBA8
0x1800dbe3d  mov     rax, [rax+78h]
0x1800dbe41  call    cs:__guard_dispatch_icall_fptr
0x1800dbe47  test    eax, eax
0x1800dbe49  js      loc_1800DC5CA
0x1800dbe4f  cmp     [rbp+57h+var_68], 2
0x1800dbe53  jnz     loc_1800DC5CA
0x1800dbe59  lea     r13, aCasfbytewiseme_137; "CASFBytewiseMediaStream::QueueFormatCha"...
0x1800dbe60  mov     r8d, 4F9h
0x1800dbe66  mov     rdx, r13
0x1800dbe69  lea     rcx, [rbp+57h+var_90]
0x1800dbe6d  call    sub_18000A580
0x1800dbe72  cmp     cs:byte_1801692CB, 20h ; ' '
0x1800dbe79  lea     r12, stru_180158D48
0x1800dbe80  jb      short loc_1800DBE9F
0x1800dbe82  mov     rcx, cs:RequestContext
0x1800dbe89  lea     edx, [r15+65h]
0x1800dbe8d  mov     r9, rdi
0x1800dbe90  mov     r8, r12
0x1800dbe93  mov     rcx, [rcx+88h]
0x1800dbe9a  call    sub_1800520C4
0x1800dbe9f  cmp     [rbp+57h+var_78], r15b
0x1800dbea3  jz      loc_1800DC5C1
0x1800dbea9  cmp     [rbp+57h+var_77], r15b
0x1800dbead  jz      loc_1800DC5C1
0x1800dbeb3  mov     dword ptr [rbp+57h+ppMFType], r15d
0x1800dbeb7  mov     [rbp+57h+var_8C], r15d
0x1800dbebb  cmp     [rdi+4E0h], r15
0x1800dbec2  jnz     loc_1800DBF83
0x1800dbec8  mov     rcx, rdi
0x1800dbecb  call    sub_18002D560
0x1800dbed0  mov     ebx, eax
0x1800dbed2  test    eax, eax
0x1800dbed4  jns     loc_1800DBF83
0x1800dbeda  mov     rcx, cs:qword_180169350
0x1800dbee1  test    rcx, rcx
0x1800dbee4  jnz     short loc_1800DBF28
0x1800dbee6  call    cs:MFGetCallStackTracingWeakReference
0x1800dbeec  mov     cs:qword_180169350, rax
0x1800dbef3  mov     rcx, rax
0x1800dbef6  test    rax, rax
0x1800dbef9  jz      short loc_1800DBF1A
0x1800dbefb  mov     rax, [rax]
0x1800dbefe  mov     edx, 7F0h
0x1800dbf03  mov     rax, [rax+8]
0x1800dbf07  call    cs:__guard_dispatch_icall_fptr
0x1800dbf0d  test    eax, eax
0x1800dbf0f  jz      short loc_1800DBF1A
0x1800dbf11  mov     rcx, cs:qword_180169350
0x1800dbf18  jmp     short loc_1800DBF28
0x1800dbf1a  lea     rcx, off_1801683B0
0x1800dbf21  mov     cs:qword_180169350, rcx
0x1800dbf28  cmp     [rcx+8], r15b
0x1800dbf2c  jz      short loc_1800DBF4F
0x1800dbf2e  call    sub_180001870
0x1800dbf33  cmp     [rax+7CCh], ebx
0x1800dbf39  jz      short loc_1800DBF4F
0x1800dbf3b  mov     r9d, ebx
0x1800dbf3e  mov     r8d, 50Ah
0x1800dbf44  mov     rdx, r13
0x1800dbf47  mov     rcx, rax
0x1800dbf4a  call    sub_18007FDD0
0x1800dbf4f  mov     esi, 1
0x1800dbf54  cmp     cs:byte_1801692C8, sil
0x1800dbf5b  jb      loc_1800DC5C1
0x1800dbf61  mov     rcx, cs:RequestContext
0x1800dbf68  lea     edx, [rsi+65h]
0x1800dbf6b  mov     r9, rdi
0x1800dbf6e  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x1800dbf72  mov     r8, r12
0x1800dbf75  mov     rcx, [rcx+10h]
0x1800dbf79  call    sub_18004F390
0x1800dbf7e  jmp     loc_1800DC5C1
0x1800dbf83  mov     rcx, [rdi+4E0h]
0x1800dbf8a  lea     r9, [rbp+57h+var_8C]
0x1800dbf8e  lea     r8, [rbp+57h+ppMFType]
0x1800dbf92  lea     rdx, qword_18014EBD0
0x1800dbf99  call    sub_18004F28C
0x1800dbf9e  mov     ebx, eax
0x1800dbfa0  mov     esi, 1
0x1800dbfa5  test    eax, eax
0x1800dbfa7  jns     short loc_1800DBFB2
0x1800dbfa9  mov     ecx, esi
0x1800dbfab  mov     edx, esi
0x1800dbfad  mov     ebx, r15d
0x1800dbfb0  jmp     short loc_1800DBFB8
0x1800dbfb2  mov     ecx, dword ptr [rbp+57h+ppMFType]
0x1800dbfb5  mov     edx, [rbp+57h+var_8C]
0x1800dbfb8  movzx   eax, [rbp+57h+var_78]
0x1800dbfbc  cmp     ecx, eax
0x1800dbfbe  jnz     short loc_1800DBFCB
0x1800dbfc0  movzx   eax, [rbp+57h+var_77]
0x1800dbfc4  mov     ecx, r15d
0x1800dbfc7  cmp     edx, eax
0x1800dbfc9  jz      short loc_1800DBFCD
0x1800dbfcb  mov     ecx, esi
0x1800dbfcd  mov     al, [rdi+4ECh]
0x1800dbfd3  test    al, al
0x1800dbfd5  jz      short loc_1800DBFDC
0x1800dbfd7  cmp     [rbp+57h+var_78], al
0x1800dbfda  jnz     short loc_1800DBFEB
0x1800dbfdc  mov     al, [rdi+4EDh]
0x1800dbfe2  test    al, al
0x1800dbfe4  jz      short loc_1800DBFEF
0x1800dbfe6  cmp     [rbp+57h+var_77], al
0x1800dbfe9  jz      short loc_1800DBFEF
0x1800dbfeb  mov     eax, esi
0x1800dbfed  jmp     short loc_1800DBFF2
0x1800dbfef  mov     eax, r15d
0x1800dbff2  test    ecx, ecx
0x1800dbff4  jnz     short loc_1800DBFFE
0x1800dbff6  test    eax, eax
0x1800dbff8  jz      loc_1800DC5C1
0x1800dbffe  cmp     cs:byte_1801692CB, 8
0x1800dc005  jb      short loc_1800DC025
0x1800dc007  mov     rcx, cs:RequestContext
0x1800dc00e  mov     edx, 67h ; 'g'
0x1800dc013  mov     r9, rdi
0x1800dc016  mov     r8, r12
0x1800dc019  mov     rcx, [rcx+88h]
0x1800dc020  call    sub_1800520C4
0x1800dc025  lea     rcx, [rbp+57h+ppMFType]; ppMFType
0x1800dc029  mov     [rbp+57h+ppMFType], r15
0x1800dc02d  mov     [rbp+57h+var_88], r15
0x1800dc031  mov     [rbp+57h+ppWrap], r15
0x1800dc035  mov     [rbp+57h+var_8C], r15d
0x1800dc039  call    cs:MFCreateMediaType
0x1800dc03f  mov     ebx, eax
0x1800dc041  test    eax, eax
0x1800dc043  jns     loc_1800DC0EF
0x1800dc049  mov     rcx, cs:qword_180169350
0x1800dc050  test    rcx, rcx
0x1800dc053  jnz     short loc_1800DC097
0x1800dc055  call    cs:MFGetCallStackTracingWeakReference
0x1800dc05b  mov     cs:qword_180169350, rax
0x1800dc062  mov     rcx, rax
0x1800dc065  test    rax, rax
0x1800dc068  jz      short loc_1800DC089
0x1800dc06a  mov     rax, [rax]
0x1800dc06d  mov     edx, 7F0h
0x1800dc072  mov     rax, [rax+8]
0x1800dc076  call    cs:__guard_dispatch_icall_fptr
0x1800dc07c  test    eax, eax
0x1800dc07e  jz      short loc_1800DC089
0x1800dc080  mov     rcx, cs:qword_180169350
0x1800dc087  jmp     short loc_1800DC097
0x1800dc089  lea     rcx, off_1801683B0
0x1800dc090  mov     cs:qword_180169350, rcx
0x1800dc097  cmp     [rcx+8], r15b
0x1800dc09b  jz      short loc_1800DC0BE
0x1800dc09d  call    sub_180001870
0x1800dc0a2  cmp     [rax+7CCh], ebx
0x1800dc0a8  jz      short loc_1800DC0BE
0x1800dc0aa  mov     r9d, ebx
0x1800dc0ad  mov     r8d, 531h
0x1800dc0b3  mov     rdx, r13
0x1800dc0b6  mov     rcx, rax
0x1800dc0b9  call    sub_18007FDD0
0x1800dc0be  cmp     cs:byte_1801692C8, sil
0x1800dc0c5  jb      loc_1800DC5A6
0x1800dc0cb  mov     edx, 68h ; 'h'
0x1800dc0d0  mov     rcx, cs:RequestContext
0x1800dc0d7  mov     r9, rdi
0x1800dc0da  mov     r8, r12
0x1800dc0dd  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x1800dc0e1  mov     rcx, [rcx+10h]
0x1800dc0e5  call    sub_18004F390
0x1800dc0ea  jmp     loc_1800DC5A6
0x1800dc0ef  mov     rcx, [rdi+4E0h]
0x1800dc0f6  mov     rdx, [rbp+57h+ppMFType]
0x1800dc0fa  mov     rax, [rcx]
0x1800dc0fd  mov     rax, [rax+100h]
0x1800dc104  call    cs:__guard_dispatch_icall_fptr
0x1800dc10a  mov     ebx, eax
0x1800dc10c  test    eax, eax
0x1800dc10e  jns     loc_1800DC1A0
0x1800dc114  mov     rcx, cs:qword_180169350
0x1800dc11b  test    rcx, rcx
0x1800dc11e  jnz     short loc_1800DC162
0x1800dc120  call    cs:MFGetCallStackTracingWeakReference
0x1800dc126  mov     cs:qword_180169350, rax
0x1800dc12d  mov     rcx, rax
0x1800dc130  test    rax, rax
0x1800dc133  jz      short loc_1800DC154
0x1800dc135  mov     rax, [rax]
0x1800dc138  mov     edx, 7F0h
0x1800dc13d  mov     rax, [rax+8]
0x1800dc141  call    cs:__guard_dispatch_icall_fptr
0x1800dc147  test    eax, eax
0x1800dc149  jz      short loc_1800DC154
0x1800dc14b  mov     rcx, cs:qword_180169350
0x1800dc152  jmp     short loc_1800DC162
0x1800dc154  lea     rcx, off_1801683B0
0x1800dc15b  mov     cs:qword_180169350, rcx
0x1800dc162  cmp     [rcx+8], r15b
0x1800dc166  jz      short loc_1800DC189
0x1800dc168  call    sub_180001870
0x1800dc16d  cmp     [rax+7CCh], ebx
0x1800dc173  jz      short loc_1800DC189
0x1800dc175  mov     r9d, ebx
0x1800dc178  mov     r8d, 533h
0x1800dc17e  mov     rdx, r13
0x1800dc181  mov     rcx, rax
0x1800dc184  call    sub_18007FDD0
0x1800dc189  cmp     cs:byte_1801692C8, sil
0x1800dc190  jb      loc_1800DC5A6
0x1800dc196  mov     edx, 69h ; 'i'
0x1800dc19b  jmp     loc_1800DC0D0
0x1800dc1a0  movzx   eax, [rbp+57h+var_77]
0x1800dc1a4  lea     rdx, qword_18014EBD0
0x1800dc1ab  mov     rcx, [rbp+57h+ppMFType]
0x1800dc1af  movzx   r8d, [rbp+57h+var_78]
0x1800dc1b4  shl     r8, 20h
0x1800dc1b8  or      r8, rax
0x1800dc1bb  mov     r9, [rcx]
0x1800dc1be  mov     rax, [r9+0B0h]
0x1800dc1c5  call    cs:__guard_dispatch_icall_fptr
0x1800dc1cb  mov     ebx, eax
0x1800dc1cd  test    eax, eax
0x1800dc1cf  jns     loc_1800DC261
0x1800dc1d5  mov     rcx, cs:qword_180169350
0x1800dc1dc  test    rcx, rcx
0x1800dc1df  jnz     short loc_1800DC223
0x1800dc1e1  call    cs:MFGetCallStackTracingWeakReference
0x1800dc1e7  mov     cs:qword_180169350, rax
0x1800dc1ee  mov     rcx, rax
0x1800dc1f1  test    rax, rax
0x1800dc1f4  jz      short loc_1800DC215
0x1800dc1f6  mov     rax, [rax]
0x1800dc1f9  mov     edx, 7F0h
0x1800dc1fe  mov     rax, [rax+8]
0x1800dc202  call    cs:__guard_dispatch_icall_fptr
0x1800dc208  test    eax, eax
0x1800dc20a  jz      short loc_1800DC215
0x1800dc20c  mov     rcx, cs:qword_180169350
0x1800dc213  jmp     short loc_1800DC223
0x1800dc215  lea     rcx, off_1801683B0
0x1800dc21c  mov     cs:qword_180169350, rcx
0x1800dc223  cmp     [rcx+8], r15b
0x1800dc227  jz      short loc_1800DC24A
0x1800dc229  call    sub_180001870
0x1800dc22e  cmp     [rax+7CCh], ebx
0x1800dc234  jz      short loc_1800DC24A
0x1800dc236  mov     r9d, ebx
0x1800dc239  mov     r8d, 538h
0x1800dc23f  mov     rdx, r13
0x1800dc242  mov     rcx, rax
0x1800dc245  call    sub_18007FDD0
0x1800dc24a  cmp     cs:byte_1801692C8, sil
0x1800dc251  jb      loc_1800DC5A6
0x1800dc257  mov     edx, 6Ah ; 'j'
0x1800dc25c  jmp     loc_1800DC0D0
0x1800dc261  lea     r8, [rbp+57h+var_88]
0x1800dc265  mov     rcx, rdi
0x1800dc268  lea     rdx, [rbp+57h+var_8C]
0x1800dc26c  call    sub_1800DA3BC
0x1800dc271  mov     ebx, eax
0x1800dc273  test    eax, eax
0x1800dc275  jns     loc_1800DC307
0x1800dc27b  mov     rcx, cs:qword_180169350
0x1800dc282  test    rcx, rcx
0x1800dc285  jnz     short loc_1800DC2C9
0x1800dc287  call    cs:MFGetCallStackTracingWeakReference
0x1800dc28d  mov     cs:qword_180169350, rax
0x1800dc294  mov     rcx, rax
0x1800dc297  test    rax, rax
0x1800dc29a  jz      short loc_1800DC2BB
0x1800dc29c  mov     rax, [rax]
0x1800dc29f  mov     edx, 7F0h
0x1800dc2a4  mov     rax, [rax+8]
0x1800dc2a8  call    cs:__guard_dispatch_icall_fptr
0x1800dc2ae  test    eax, eax
0x1800dc2b0  jz      short loc_1800DC2BB
0x1800dc2b2  mov     rcx, cs:qword_180169350
  ... truncated ...
```
