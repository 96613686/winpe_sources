# ProcessEventSupplicant

- ea: `0x18000ba30`
- end: `0x18000c3e4`
- name: `ProcessEventSupplicant`
- size: `2484`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x18000b330`

## callees

- `0x180005440`
- `0x180007f60`
- `0x18000ba30`
- `0x18000c3f0`
- `0x18000c4c0`
- `0x18000c5a0`
- `0x18000c630`
- `0x18000c870`
- `0x18000dd40`
- `0x180010ae0`
- `0x180010d40`
- `0x180016980`
- `0x180019f7c`
- `0x1800214f0`
- `0x180022000`
- `0x1800225d0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c2fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c2fb`
- `MobileNetworking!FreeMemory` at `0x18000bcb3`
- `MobileNetworking!FreeMemory` at `0x18000bd4b`
- `MobileNetworking!FreeMemory` at `0x18000c2dc`
- `MobileNetworking!FreeMemory` at `0x18000bcb3`
- `MobileNetworking!FreeMemory` at `0x18000bd4b`
- `MobileNetworking!FreeMemory` at `0x18000c2dc`

## string_xrefs

- `0x18000bca7`: `OneXDeleteEvent`
- `0x18000bd44`: `OneXDeleteEvent`
- `0x18000c2d5`: `OneXDeleteEvent`

## pseudocode

```c
__int64 __fastcall ProcessEventSupplicant(__int64 a1)
{
  __int64 v1; // r15
  unsigned int v3; // r13d
  __int64 v4; // r8
  unsigned int v5; // r12d
  _QWORD *v6; // r10
  _QWORD *v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rbp
  __int64 v11; // rsi
  __int64 v12; // rsi
  __int64 (__fastcall *v13)(__int64, int *); // rax
  int v14; // eax
  __int64 v15; // r14
  __int64 (__fastcall *v16)(__int64); // rax
  __int64 (__fastcall *v17)(__int64); // rax
  unsigned int v18; // eax
  __int64 BackendStateDescription; // rax
  __int64 v20; // r10
  __int64 v21; // r8
  unsigned int v22; // esi
  __int64 i; // rdi
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // r10
  __int64 SupplicantEventDescription; // rax
  __int64 v28; // r10
  __int64 (__fastcall *v29)(__int64, int *); // rax
  unsigned int v30; // eax
  int v31; // eax
  __int64 v32; // r14
  __int64 (__fastcall *v33)(__int64); // rax
  unsigned int v34; // eax
  __int64 (__fastcall *v35)(__int64); // rax
  __int64 *v36; // rbx
  __int64 v37; // rdi
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // r10
  __int64 v42; // rdx
  unsigned int v43; // eax
  unsigned int v44; // eax
  __int64 FrontEndStateDescription; // rax
  __int64 v46; // r10
  __int64 v47; // r8
  unsigned int v48; // eax
  unsigned int v49; // eax
  __int64 v50; // rcx
  void *v51; // rcx
  int v52; // [rsp+70h] [rbp+8h] BYREF
  __int64 v53; // [rsp+78h] [rbp+10h] BYREF

  v1 = *(_QWORD *)(a1 + 24);
  v3 = *(_DWORD *)(v1 + 20);
  v52 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 29, WPP_c98c90d098d532f46181864aabb10d65_Traceguids);
  v5 = MapAndQueueSupplicantEvent(v1, a1);
  if ( !v5 )
  {
LABEL_3:
    v6 = WPP_GLOBAL_Control;
    while ( 1 )
    {
      v7 = (_QWORD *)(v1 + 2808);
      v8 = *(_QWORD *)(v1 + 2808);
      if ( v8 == v1 + 2808 )
        goto LABEL_63;
      if ( *(_QWORD **)(v8 + 8) != v7 || (v9 = *(_QWORD *)v8, *(_QWORD *)(*(_QWORD *)v8 + 8LL) != v8) )
LABEL_135:
        __fastfail(3u);
      *v7 = v9;
      *(_QWORD *)(v9 + 8) = v7;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x40) != 0 )
      {
        SupplicantEventDescription = GetSupplicantEventDescription(*(unsigned int *)(v8 + 16));
        WPP_SF_dS(
          *(_QWORD *)(v28 + 56),
          31,
          (unsigned int)WPP_c98c90d098d532f46181864aabb10d65_Traceguids,
          v3,
          SupplicantEventDescription);
        v6 = WPP_GLOBAL_Control;
      }
      v10 = *(int *)(v1 + 2400);
      v11 = 16LL * *(unsigned int *)(v8 + 16) + SPAETransitionTable[v10];
      if ( *(_DWORD *)(v11 + 8) )
      {
        v29 = (__int64 (__fastcall *)(__int64, int *))SPAEStateTable[4 * v10 + 1];
        if ( v29 )
        {
          v30 = v29(v8, &v52);
          v6 = WPP_GLOBAL_Control;
          v5 = v30;
          v31 = v52;
        }
        else
        {
          v31 = 1;
          v52 = 1;
        }
        if ( v5 )
        {
          if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 68) & 1) != 0 )
          {
            WPP_SF_ddD(v6[7], 32, v4, v3, v10, v5);
            v6 = WPP_GLOBAL_Control;
          }
          v5 = 0;
          goto LABEL_25;
        }
        if ( v31 )
        {
          v32 = *(int *)(v11 + 8);
          v33 = (__int64 (__fastcall *)(__int64))SPAEStateTable[4 * v10 + 3];
          if ( v33 )
          {
            v34 = v33(v8);
            v5 = v34;
            if ( v34 )
            {
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
              {
                goto LABEL_94;
              }
              v42 = 33;
              goto LABEL_92;
            }
            v6 = WPP_GLOBAL_Control;
          }
          if ( *(_QWORD *)v11 )
          {
            v43 = (*(__int64 (__fastcall **)(__int64))v11)(v8);
            v5 = v43;
            if ( v43 )
            {
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
              {
                WPP_SF_ddD(*((_QWORD *)WPP_GLOBAL_Control + 7), 34, v4, v3, *(_DWORD *)(v8 + 16), v43);
                goto LABEL_93;
              }
              goto LABEL_94;
            }
            v6 = WPP_GLOBAL_Control;
          }
          v35 = (__int64 (__fastcall *)(__int64))SPAEStateTable[4 * v32 + 2];
          if ( v35 )
          {
            v44 = v35(v8);
            v5 = v44;
            if ( v44 )
            {
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
              {
                WPP_SF_ddD(*((_QWORD *)WPP_GLOBAL_Control + 7), 35, v4, v3, v32, v44);
                goto LABEL_93;
              }
              goto LABEL_94;
            }
            v6 = WPP_GLOBAL_Control;
          }
          if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 68) & 0x40) != 0 )
          {
            GetFrontEndStateDescription((unsigned int)v32);
            FrontEndStateDescription = GetFrontEndStateDescription((unsigned int)v10);
            WPP_SF_dSS(
              *(_QWORD *)(v46 + 56),
              14,
              (unsigned int)WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids,
              *(_DWORD *)(v1 + 20),
              FrontEndStateDescription,
              v47);
          }
          *(_DWORD *)(v1 + 2400) = v32;
          MSMNotifyStateChange(v1);
          v6 = WPP_GLOBAL_Control;
        }
      }
      v10 = *(int *)(v1 + 2464);
      v12 = 16LL * *(unsigned int *)(v8 + 16) + SBackendTransitionTable[v10];
      if ( *(_DWORD *)(v12 + 8) )
      {
        v13 = (__int64 (__fastcall *)(__int64, int *))SBackendStateTable[4 * v10 + 1];
        if ( v13 )
        {
          v48 = v13(v8, &v52);
          v6 = WPP_GLOBAL_Control;
          v5 = v48;
          v14 = v52;
        }
        else
        {
          v14 = 1;
          v52 = 1;
        }
        if ( v5 )
        {
          if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 68) & 1) != 0 )
            WPP_SF_ddD(v6[7], 36, v4, v3, v10, v5);
          OneXDeleteEvent(v8);
LABEL_62:
          v6 = WPP_GLOBAL_Control;
          goto LABEL_63;
        }
        if ( v14 )
        {
          v15 = *(int *)(v12 + 8);
          v16 = (__int64 (__fastcall *)(__int64))SBackendStateTable[4 * v10 + 3];
          if ( v16 )
          {
            v34 = v16(v8);
            v5 = v34;
            if ( v34 )
            {
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
              {
                goto LABEL_94;
              }
              v42 = 37;
LABEL_92:
              WPP_SF_ddD(v6[7], v42, v4, v3, v10, v34);
              goto LABEL_93;
            }
            v6 = WPP_GLOBAL_Control;
          }
          if ( *(_QWORD *)v12 )
          {
            v49 = (*(__int64 (__fastcall **)(__int64))v12)(v8);
            v5 = v49;
            if ( v49 )
            {
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
              {
                WPP_SF_ddD(*((_QWORD *)WPP_GLOBAL_Control + 7), 38, v4, v3, *(_DWORD *)(v8 + 16), v49);
                goto LABEL_93;
              }
LABEL_94:
              v5 = 0;
              goto LABEL_25;
            }
            v6 = WPP_GLOBAL_Control;
          }
          v17 = (__int64 (__fastcall *)(__int64))SBackendStateTable[4 * v15 + 2];
          if ( v17 )
          {
            v18 = v17(v8);
            v5 = v18;
            if ( v18 )
            {
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
              {
                WPP_SF_ddD(*((_QWORD *)WPP_GLOBAL_Control + 7), 39, v4, v3, v15, v18);
LABEL_93:
                v6 = WPP_GLOBAL_Control;
              }
              goto LABEL_94;
            }
            v6 = WPP_GLOBAL_Control;
          }
          if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 68) & 0x40) != 0 )
          {
            GetBackendStateDescription((unsigned int)v15);
            BackendStateDescription = GetBackendStateDescription((unsigned int)v10);
            WPP_SF_dSS(
              *(_QWORD *)(v20 + 56),
              14,
              (unsigned int)WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids,
              *(_DWORD *)(v1 + 20),
              BackendStateDescription,
              v21);
          }
          *(_DWORD *)(v1 + 2464) = v15;
          if ( (*(_BYTE *)(v1 + 24) & 1) != 0 )
            MSMNotifyStateChange(v1);
          v6 = WPP_GLOBAL_Control;
        }
      }
LABEL_25:
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 68) & 0x40) != 0 )
      {
        v25 = GetSupplicantEventDescription(*(unsigned int *)(v8 + 16));
        WPP_SF_dS(*(_QWORD *)(v26 + 56), 40, (unsigned int)WPP_c98c90d098d532f46181864aabb10d65_Traceguids, v3, v25);
        v6 = WPP_GLOBAL_Control;
      }
      v53 = v8;
      if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 17) & 0x800) != 0 )
      {
        WPP_SF_(v6[7], 17, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
        v6 = WPP_GLOBAL_Control;
        v8 = v53;
      }
      if ( v8 )
      {
        v22 = 0;
        for ( i = 0; (unsigned int)i < *(_DWORD *)(v8 + 32); i = (unsigned int)(i + 1) )
        {
          v24 = 16LL * (unsigned int)i;
          switch ( *(_DWORD *)(v24 + v8 + 40) )
          {
            case 3:
              v51 = *(void **)(v8 + 16 * (i + 3));
              if ( !v51 )
                continue;
              CloseHandle(v51);
              break;
            case 5:
              FreeMemory(v24 + v8 + 48, "OneXDeleteEvent", 158);
              break;
            case 6:
              FreeMemory(v24 + v8 + 48, "OneXDeleteEvent", 162);
              break;
            case 7:
              v50 = *(_QWORD *)(v8 + 16 * (i + 3));
              if ( !v50 )
                continue;
              FreeEapAttributes(v50);
              break;
            default:
              if ( *(_DWORD *)(v24 + v8 + 40) != 8 || !*(_QWORD *)(v8 + 16 * (i + 3)) )
                continue;
              OneXFreeRuntimeState();
              break;
          }
          v8 = v53;
        }
        FreeMemory(&v53, "OneXDeleteEvent", 190);
        goto LABEL_38;
      }
      if ( v6 != &WPP_GLOBAL_Control )
      {
        v22 = 87;
        if ( (*((_BYTE *)v6 + 68) & 1) != 0 )
        {
          WPP_SF_d(v6[7], 18, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, 0);
LABEL_38:
          v6 = WPP_GLOBAL_Control;
        }
        if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 17) & 0x800) != 0 )
        {
          WPP_SF_D(v6[7], 19, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v22);
          goto LABEL_3;
        }
      }
    }
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 30, WPP_c98c90d098d532f46181864aabb10d65_Traceguids, v3, v5);
    goto LABEL_62;
  }
LABEL_63:
  v36 = (__int64 *)(v1 + 2808);
  if ( v6 == &WPP_GLOBAL_Control )
    goto LABEL_67;
  if ( (*((_DWORD *)v6 + 17) & 0x800) != 0 )
  {
    WPP_SF_(v6[7], 46, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 68) & 0x40) == 0 )
    goto LABEL_67;
  WPP_SF_dS(v6[7], 47, (unsigned int)WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v3, (__int64)L"SupplicantQueue");
  while ( 1 )
  {
    v6 = WPP_GLOBAL_Control;
LABEL_67:
    v37 = *v36;
    if ( (__int64 *)*v36 == v36 )
      break;
    if ( *(__int64 **)(v37 + 8) != v36 )
      goto LABEL_135;
    v39 = *(_QWORD *)v37;
    if ( *(_QWORD *)(*(_QWORD *)v37 + 8LL) != v37 )
      goto LABEL_135;
    *v36 = v39;
    *(_QWORD *)(v39 + 8) = v36;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x40) != 0 )
    {
      v40 = GetSupplicantEventDescription(*(unsigned int *)(v37 + 16));
      WPP_SF_dSS(
        *(_QWORD *)(v41 + 56),
        49,
        (unsigned int)WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids,
        v3,
        v40,
        (__int64)L"SupplicantQueue");
    }
    OneXDeleteEvent(v37);
  }
  if ( v6 != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)v6 + 17) & 0x800) != 0 )
    {
      WPP_SF_D(v6[7], 50, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, 0);
      v6 = WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 17) & 0x800) != 0 )
      WPP_SF_D(v6[7], 41, WPP_c98c90d098d532f46181864aabb10d65_Traceguids, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x18000ba30  push    rbx
0x18000ba32  push    r12
0x18000ba34  push    r13
0x18000ba36  push    r15
0x18000ba38  sub     rsp, 48h
0x18000ba3c  mov     r15, [rcx+18h]
0x18000ba40  mov     rbx, rcx
0x18000ba43  mov     r13d, [r15+14h]
0x18000ba47  mov     [rsp+68h+arg_0], 0
0x18000ba4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba56  lea     rax, WPP_GLOBAL_Control
0x18000ba5d  cmp     rcx, rax
0x18000ba60  jnz     loc_18000BF84
0x18000ba66  mov     [rsp+68h+arg_10], rbp
0x18000ba6e  mov     rdx, rbx
0x18000ba71  mov     [rsp+68h+var_28], rsi
0x18000ba76  mov     rcx, r15
0x18000ba79  mov     [rsp+68h+var_30], rdi
0x18000ba7e  mov     [rsp+68h+var_38], r14
0x18000ba83  call    MapAndQueueSupplicantEvent
0x18000ba88  mov     r12d, eax
0x18000ba8b  test    eax, eax
0x18000ba8d  jnz     loc_18000BFAB
0x18000ba93  lea     r14, __ImageBase
0x18000ba9a  mov     r10, cs:WPP_GLOBAL_Control
0x18000baa1  lea     rax, [r15+0AF8h]
0x18000baa8  mov     rbx, [rax]
0x18000baab  cmp     rbx, rax
0x18000baae  jz      loc_18000BE9A
0x18000bab4  cmp     [rbx+8], rax
0x18000bab8  jnz     loc_18000C38E
0x18000babe  mov     rcx, [rbx]
0x18000bac1  cmp     [rcx+8], rbx
0x18000bac5  jnz     loc_18000C38E
0x18000bacb  mov     [rax], rcx
0x18000bace  mov     [rcx+8], rax
0x18000bad2  mov     r10, cs:WPP_GLOBAL_Control
0x18000bad9  lea     rax, WPP_GLOBAL_Control
0x18000bae0  cmp     r10, rax
0x18000bae3  jnz     loc_18000BD5B
0x18000bae9  movsxd  rbp, dword ptr [r15+960h]
0x18000baf0  mov     ecx, [rbx+10h]
0x18000baf3  mov     rdi, rbp
0x18000baf6  shl     rcx, 4
0x18000bafa  mov     rsi, rva SPAETransitionTable[r14+rbp*8]
0x18000bb02  add     rsi, rcx
0x18000bb05  cmp     dword ptr [rsi+8], 0
0x18000bb09  jnz     loc_18000BD97
0x18000bb0f  movsxd  rbp, dword ptr [r15+9A0h]
0x18000bb16  mov     ecx, [rbx+10h]
0x18000bb19  mov     rdi, rbp
0x18000bb1c  shl     rcx, 4
0x18000bb20  mov     rsi, rva SBackendTransitionTable[r14+rbp*8]
0x18000bb28  add     rsi, rcx
0x18000bb2b  cmp     dword ptr [rsi+8], 0
0x18000bb2f  jz      loc_18000BC29
0x18000bb35  shl     rdi, 5
0x18000bb39  mov     rax, [rdi+r14+3E008h]
0x18000bb41  test    rax, rax
0x18000bb44  jnz     loc_18000C15F
0x18000bb4a  mov     eax, 1
0x18000bb4f  mov     [rsp+68h+arg_0], eax
0x18000bb53  test    r12d, r12d
0x18000bb56  jnz     loc_18000C306
0x18000bb5c  test    eax, eax
0x18000bb5e  jz      loc_18000BC29
0x18000bb64  movsxd  r14, dword ptr [rsi+8]
0x18000bb68  lea     rax, __ImageBase
0x18000bb6f  mov     rax, [rdi+rax+3E018h]
0x18000bb77  test    rax, rax
0x18000bb7a  jnz     loc_18000C17F
0x18000bb80  mov     rax, [rsi]
0x18000bb83  test    rax, rax
0x18000bb86  jnz     loc_18000C1C1
0x18000bb8c  mov     rax, r14
0x18000bb8f  lea     rcx, __ImageBase
0x18000bb96  shl     rax, 5
0x18000bb9a  mov     rax, [rax+rcx+3E010h]
0x18000bba2  test    rax, rax
0x18000bba5  jz      short loc_18000BBC1
0x18000bba7  mov     rcx, rbx
0x18000bbaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbaf  mov     r12d, eax
0x18000bbb2  test    eax, eax
0x18000bbb4  jnz     loc_18000C213
0x18000bbba  mov     r10, cs:WPP_GLOBAL_Control
0x18000bbc1  lea     rax, WPP_GLOBAL_Control
0x18000bbc8  cmp     r10, rax
0x18000bbcb  jz      short loc_18000BC09
0x18000bbcd  test    byte ptr [r10+44h], 40h
0x18000bbd2  jz      short loc_18000BC09
0x18000bbd4  mov     ecx, r14d
0x18000bbd7  call    GetBackendStateDescription
0x18000bbdc  mov     ecx, ebp
0x18000bbde  mov     r8, rax
0x18000bbe1  call    GetBackendStateDescription
0x18000bbe6  mov     rcx, [r10+38h]
0x18000bbea  mov     edx, 0Eh
0x18000bbef  mov     r9d, [r15+14h]
0x18000bbf3  mov     [rsp+68h+var_40], r8
0x18000bbf8  lea     r8, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids
0x18000bbff  mov     [rsp+68h+var_48], rax
0x18000bc04  call    WPP_SF_dSS
0x18000bc09  mov     [r15+9A0h], r14d
0x18000bc10  test    byte ptr [r15+18h], 1
0x18000bc15  jnz     loc_18000C23A
0x18000bc1b  mov     r10, cs:WPP_GLOBAL_Control
0x18000bc22  lea     r14, __ImageBase
0x18000bc29  lea     rdi, WPP_GLOBAL_Control
0x18000bc30  cmp     r10, rdi
0x18000bc33  jnz     loc_18000BCFB
0x18000bc39  mov     [rsp+68h+arg_8], rbx
0x18000bc3e  cmp     r10, rdi
0x18000bc41  jz      short loc_18000BC51
0x18000bc43  test    dword ptr [r10+44h], 800h
0x18000bc4b  jnz     loc_18000C247
0x18000bc51  test    rbx, rbx
0x18000bc54  jz      loc_18000C26D
0x18000bc5a  xor     esi, esi
0x18000bc5c  xor     edi, edi
0x18000bc5e  cmp     [rbx+20h], esi
0x18000bc61  jbe     short loc_18000BCA1
0x18000bc63  mov     edx, edi
0x18000bc65  shl     rdx, 4
0x18000bc69  mov     ecx, [rdx+rbx+28h]
0x18000bc6d  sub     ecx, 3
0x18000bc70  jz      loc_18000C2E7
0x18000bc76  sub     ecx, 2
0x18000bc79  jz      loc_18000C2C8
0x18000bc7f  sub     ecx, 1
0x18000bc82  jz      loc_18000BD37
0x18000bc88  sub     ecx, 1
0x18000bc8b  jz      loc_18000C2AA
0x18000bc91  cmp     ecx, 1
0x18000bc94  jz      loc_18000BE67
0x18000bc9a  inc     edi
0x18000bc9c  cmp     edi, [rbx+20h]
0x18000bc9f  jb      short loc_18000BC63
0x18000bca1  mov     r8d, 0BEh
0x18000bca7  lea     rdx, aOnexdeleteeven; "OneXDeleteEvent"
0x18000bcae  lea     rcx, [rsp+68h+arg_8]
0x18000bcb3  call    cs:__imp_FreeMemory
0x18000bcb9  lea     rbx, WPP_GLOBAL_Control
0x18000bcc0  mov     r10, cs:WPP_GLOBAL_Control
0x18000bcc7  cmp     r10, rbx
0x18000bcca  jz      loc_18000BAA1
0x18000bcd0  test    dword ptr [r10+44h], 800h
0x18000bcd8  jz      loc_18000BAA1
0x18000bcde  mov     rcx, [r10+38h]
0x18000bce2  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000bce9  mov     edx, 13h
0x18000bcee  mov     r9d, esi
0x18000bcf1  call    WPP_SF_D
0x18000bcf6  jmp     loc_18000BA9A
0x18000bcfb  test    byte ptr [r10+44h], 40h
0x18000bd00  jz      loc_18000BC39
0x18000bd06  mov     ecx, [rbx+10h]
0x18000bd09  call    GetSupplicantEventDescription
0x18000bd0e  mov     rcx, [r10+38h]
0x18000bd12  lea     r8, WPP_c98c90d098d532f46181864aabb10d65_Traceguids
0x18000bd19  mov     edx, 28h ; '('
0x18000bd1e  mov     [rsp+68h+var_48], rax
0x18000bd23  mov     r9d, r13d
0x18000bd26  call    WPP_SF_dS
0x18000bd2b  mov     r10, cs:WPP_GLOBAL_Control
0x18000bd32  jmp     loc_18000BC39
0x18000bd37  lea     rcx, [rbx+30h]
0x18000bd3b  mov     r8d, 0A2h
0x18000bd41  add     rcx, rdx
0x18000bd44  lea     rdx, aOnexdeleteeven; "OneXDeleteEvent"
0x18000bd4b  call    cs:__imp_FreeMemory
0x18000bd51  mov     rbx, [rsp+68h+arg_8]
0x18000bd56  jmp     loc_18000BC9A
0x18000bd5b  test    byte ptr [r10+44h], 40h
0x18000bd60  jz      loc_18000BAE9
0x18000bd66  mov     ecx, [rbx+10h]
0x18000bd69  call    GetSupplicantEventDescription
0x18000bd6e  mov     rcx, [r10+38h]
0x18000bd72  lea     r8, WPP_c98c90d098d532f46181864aabb10d65_Traceguids
0x18000bd79  mov     edx, 1Fh
0x18000bd7e  mov     [rsp+68h+var_48], rax
0x18000bd83  mov     r9d, r13d
0x18000bd86  call    WPP_SF_dS
0x18000bd8b  mov     r10, cs:WPP_GLOBAL_Control
0x18000bd92  jmp     loc_18000BAE9
0x18000bd97  shl     rdi, 5
0x18000bd9b  mov     rax, [rdi+r14+3E208h]
0x18000bda3  test    rax, rax
0x18000bda6  jz      loc_18000BE85
0x18000bdac  lea     rdx, [rsp+68h+arg_0]
0x18000bdb1  mov     rcx, rbx
0x18000bdb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdb9  mov     r10, cs:WPP_GLOBAL_Control
0x18000bdc0  mov     r12d, eax
0x18000bdc3  mov     eax, [rsp+68h+arg_0]
0x18000bdc7  test    r12d, r12d
0x18000bdca  jnz     loc_18000BFEF
0x18000bdd0  test    eax, eax
0x18000bdd2  jz      loc_18000BB0F
0x18000bdd8  movsxd  r14, dword ptr [rsi+8]
0x18000bddc  lea     rax, __ImageBase
0x18000bde3  mov     rax, [rdi+rax+3E218h]
0x18000bdeb  test    rax, rax
0x18000bdee  jz      short loc_18000BE0A
0x18000bdf0  mov     rcx, rbx
0x18000bdf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdf8  mov     r12d, eax
0x18000bdfb  test    eax, eax
0x18000bdfd  jnz     loc_18000C02B
0x18000be03  mov     r10, cs:WPP_GLOBAL_Control
0x18000be0a  mov     rax, [rsi]
0x18000be0d  test    rax, rax
0x18000be10  jnz     loc_18000C08B
0x18000be16  mov     rax, r14
0x18000be19  lea     rcx, __ImageBase
0x18000be20  shl     rax, 5
0x18000be24  mov     rax, [rax+rcx+3E210h]
0x18000be2c  test    rax, rax
0x18000be2f  jnz     loc_18000C0D2
0x18000be35  lea     rax, WPP_GLOBAL_Control
0x18000be3c  cmp     r10, rax
0x18000be3f  jnz     loc_18000C11A
0x18000be45  mov     rcx, r15
0x18000be48  mov     [r15+960h], r14d
0x18000be4f  call    MSMNotifyStateChange
0x18000be54  mov     r10, cs:WPP_GLOBAL_Control
0x18000be5b  lea     r14, __ImageBase
0x18000be62  jmp     loc_18000BB0F
0x18000be67  lea     rax, [rdi+3]
0x18000be6b  add     rax, rax
0x18000be6e  mov     rcx, [rbx+rax*8]
0x18000be72  test    rcx, rcx
0x18000be75  jz      loc_18000BC9A
0x18000be7b  call    OneXFreeRuntimeState
0x18000be80  jmp     loc_18000BD51
0x18000be85  mov     eax, 1
0x18000be8a  mov     [rsp+68h+arg_0], eax
0x18000be8e  jmp     loc_18000BDC7
0x18000be93  mov     r10, cs:WPP_GLOBAL_Control
0x18000be9a  lea     rbx, [r15+0AF8h]
0x18000bea1  lea     r15, WPP_GLOBAL_Control
0x18000bea8  lea     rsi, aSupplicantqueu; "SupplicantQueue"
0x18000beaf  cmp     r10, r15
0x18000beb2  jz      short loc_18000BECB
0x18000beb4  test    dword ptr [r10+44h], 800h
0x18000bebc  jnz     loc_18000C340
0x18000bec2  cmp     r10, r15
0x18000bec5  jnz     loc_18000C361
0x18000becb  mov     rdi, [rbx]
0x18000bece  cmp     rdi, rbx
0x18000bed1  jnz     short loc_18000BF15
0x18000bed3  cmp     r10, r15
0x18000bed6  jz      short loc_18000BEEF
0x18000bed8  test    dword ptr [r10+44h], 800h
0x18000bee0  jnz     loc_18000C395
0x18000bee6  cmp     r10, r15
0x18000bee9  jnz     loc_18000C3B9
0x18000beef  mov     r14, [rsp+68h+var_38]
0x18000bef4  mov     eax, r12d
0x18000bef7  mov     rdi, [rsp+68h+var_30]
0x18000befc  mov     rsi, [rsp+68h+var_28]
0x18000bf01  mov     rbp, [rsp+68h+arg_10]
0x18000bf09  add     rsp, 48h
0x18000bf0d  pop     r15
0x18000bf0f  pop     r13
0x18000bf11  pop     r12
0x18000bf13  pop     rbx
0x18000bf14  retn
0x18000bf15  cmp     [rdi+8], rbx
0x18000bf19  jnz     loc_18000C38E
0x18000bf1f  mov     rax, [rdi]
0x18000bf22  cmp     [rax+8], rdi
0x18000bf26  jnz     loc_18000C38E
0x18000bf2c  mov     [rbx], rax
0x18000bf2f  mov     [rax+8], rbx
0x18000bf33  mov     r10, cs:WPP_GLOBAL_Control
0x18000bf3a  cmp     r10, r15
0x18000bf3d  jz      short loc_18000BF70
0x18000bf3f  test    byte ptr [r10+44h], 40h
0x18000bf44  jz      short loc_18000BF70
0x18000bf46  mov     ecx, [rdi+10h]
0x18000bf49  call    GetSupplicantEventDescription
0x18000bf4e  mov     rcx, [r10+38h]
0x18000bf52  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000bf59  mov     edx, 31h ; '1'
0x18000bf5e  mov     [rsp+68h+var_40], rsi
0x18000bf63  mov     r9d, r13d
0x18000bf66  mov     [rsp+68h+var_48], rax
0x18000bf6b  call    WPP_SF_dSS
0x18000bf70  mov     rcx, rdi
0x18000bf73  call    OneXDeleteEvent
0x18000bf78  mov     r10, cs:WPP_GLOBAL_Control
0x18000bf7f  jmp     loc_18000BECB
0x18000bf84  test    dword ptr [rcx+44h], 800h
0x18000bf8b  jz      loc_18000BA66
0x18000bf91  mov     rcx, [rcx+38h]
0x18000bf95  lea     r8, WPP_c98c90d098d532f46181864aabb10d65_Traceguids
0x18000bf9c  mov     edx, 1Dh
0x18000bfa1  call    WPP_SF_
0x18000bfa6  jmp     loc_18000BA66
  ... truncated ...
```
