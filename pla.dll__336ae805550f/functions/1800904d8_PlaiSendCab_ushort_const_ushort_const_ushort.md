# PlaiSendCab(ushort const *,ushort const *,ushort *)

- ea: `0x1800904d8`
- end: `0x180090ca2`
- name: `?PlaiSendCab@@YAJPEBG0PEAG@Z`
- size: `1994`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18007e10c`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x1800123d4`
- `0x180012ef0`
- `0x180015f98`
- `0x18002b3a0`
- `0x1800904d8`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090877`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090877`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180090869`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180090869`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageEx` at `0x18009071d`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageEx` at `0x180090939`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageEx` at `0x18009071d`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageEx` at `0x180090939`

## pseudocode

```c
__int64 __fastcall PlaiSendCab(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned __int16 *a3)
{
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // r14
  unsigned int v8; // ebx
  __int64 v9; // rax
  int *v10; // r9
  int *v11; // rcx
  int v12; // eax
  unsigned __int64 v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rax
  HRESULT v17; // eax
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rax
  DWORD LastError; // eax
  __int64 v22; // rax
  HRESULT v23; // eax
  __int64 v24; // rax
  int v25; // eax
  __int64 v26; // rax
  int v27; // eax
  __int64 v28; // rax
  __int64 v29; // rax
  int pStgOptions; // [rsp+20h] [rbp-E0h]
  unsigned int v32; // [rsp+70h] [rbp-90h] BYREF
  int v33; // [rsp+78h] [rbp-88h] BYREF
  void *ppObjectOpen; // [rsp+80h] [rbp-80h] BYREF
  __int64 v35; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v36[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v37[64]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v38[64]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 v39[64]; // [rsp+210h] [rbp+110h] BYREF
  unsigned __int16 v40[64]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v41[64]; // [rsp+310h] [rbp+210h] BYREF
  unsigned __int16 v42[64]; // [rsp+390h] [rbp+290h] BYREF
  unsigned __int16 v43[64]; // [rsp+410h] [rbp+310h] BYREF
  unsigned __int16 v44[64]; // [rsp+490h] [rbp+390h] BYREF
  unsigned __int16 v45[64]; // [rsp+510h] [rbp+410h] BYREF

  v35 = 0;
  ppObjectOpen = 0;
  if ( !a3 || !*a3 )
  {
    v8 = PlaiHResultFromWin32(0xA1u);
    v33 = 0;
    v32 = v8;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      return v8;
    }
    PlaiWhoAmI(v45, 0x4000000000000800uLL);
    v29 = -1;
    do
      ++v29;
    while ( v45[v29] );
    v11 = &v33;
    v10 = (int *)&v32;
LABEL_79:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v10, 4, byte_180147320, 1, v11, 4);
    goto LABEL_80;
  }
  v6 = (unsigned __int16 *)PlaiAlloc(0x800u, 1, 0, byte_180147320, pStgOptions);
  v7 = v6;
  if ( !v6 )
  {
    v8 = -2147024882;
    v33 = -2147024882;
    v32 = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_80;
    }
    PlaiWhoAmI(v36, 0x4000000000000800uLL);
    v9 = -1;
    do
      ++v9;
    while ( v36[v9] );
    v10 = &v33;
    v11 = (int *)&v32;
    goto LABEL_79;
  }
  v12 = StringCchPrintfW(v6, 0x400u, L"%s\\%s.cab", a3, a1);
  v8 = v12;
  if ( v12 < 0 )
  {
    v33 = 0;
    v32 = v12;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_72;
    }
    PlaiWhoAmI(v37, 0x4000000000000800uLL);
    v14 = -1;
    do
      ++v14;
    while ( v37[v14] );
    goto LABEL_71;
  }
  v15 = PlaiExpandVariables(v7, v13, v7);
  v8 = v15;
  if ( v15 < 0 )
  {
    v33 = 0;
    v32 = v15;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_72;
    }
    PlaiWhoAmI(v38, 0x4000000000000800uLL);
    v16 = -1;
    do
      ++v16;
    while ( v38[v16] );
    goto LABEL_71;
  }
  v17 = StgOpenStorageEx(a2, 0x12u, 3u, 0, 0, 0, &IID_IPropertySetStorage, &ppObjectOpen);
  v8 = v17;
  if ( v17 < 0 )
  {
    v33 = 0;
    v32 = v17;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_72;
    }
    PlaiWhoAmI(v39, 0x4000000000000800uLL);
    v18 = -1;
    do
      ++v18;
    while ( v39[v18] );
    goto LABEL_71;
  }
  v19 = (*(__int64 (__fastcall **)(void *, GUID *, __int64, __int64 *))(*(_QWORD *)ppObjectOpen + 32LL))(
          ppObjectOpen,
          &FMTID_PlaFileCopied,
          16,
          &v35);
  v8 = v19;
  if ( v19 < 0 )
  {
    if ( v19 == -2147287038 )
    {
      if ( ppObjectOpen )
      {
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppObjectOpen + 16LL))(ppObjectOpen);
        ppObjectOpen = 0;
      }
      if ( CopyFileW(a2, v7, 0)
        || (LastError = GetLastError(), v8 = PlaiHResultFromWin32(LastError), (int)(v8 + 0x80000000) < 0)
        || v8 == -2147024713 )
      {
        v23 = StgOpenStorageEx(a2, 0x12u, 3u, 0, 0, 0, &IID_IPropertySetStorage, &ppObjectOpen);
        v8 = v23;
        if ( v23 >= 0 )
        {
          v25 = (*(__int64 (__fastcall **)(void *, GUID *, _QWORD, _QWORD, int, __int64 *))(*(_QWORD *)ppObjectOpen
                                                                                          + 24LL))(
                  ppObjectOpen,
                  &FMTID_PlaFileCopied,
                  0,
                  0,
                  4114,
                  &v35);
          v8 = v25;
          if ( v25 >= 0 )
          {
            v27 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v35 + 72LL))(v35, 0);
            v8 = v27;
            if ( v27 >= 0 )
              goto LABEL_72;
            v33 = 0;
            v32 = v27;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_72;
            }
            PlaiWhoAmI(v44, 0x4000000000000800uLL);
            v28 = -1;
            do
              ++v28;
            while ( v44[v28] );
          }
          else
          {
            v33 = 0;
            v32 = v25;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_72;
            }
            PlaiWhoAmI(v43, 0x4000000000000800uLL);
            v26 = -1;
            do
              ++v26;
            while ( v43[v26] );
          }
        }
        else
        {
          v33 = 0;
          v32 = v23;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_72;
          }
          PlaiWhoAmI(v42, 0x4000000000000800uLL);
          v24 = -1;
          do
            ++v24;
          while ( v42[v24] );
        }
      }
      else
      {
        v33 = 0;
        v32 = v8;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_72;
        }
        PlaiWhoAmI(v41, 0x4000000000000800uLL);
        v22 = -1;
        do
          ++v22;
        while ( v41[v22] );
      }
    }
    else
    {
      v33 = 0;
      v32 = v19;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_72;
      }
      PlaiWhoAmI(v40, 0x4000000000000800uLL);
      v20 = -1;
      do
        ++v20;
      while ( v40[v20] );
    }
LABEL_71:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v32, 4, byte_180147320, 1, &v33, 4);
    goto LABEL_72;
  }
  v8 = 0;
LABEL_72:
  PlaiFree(v7, 1);
LABEL_80:
  if ( ppObjectOpen )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppObjectOpen + 16LL))(ppObjectOpen);
    ppObjectOpen = 0;
  }
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  return v8;
}

```

## disassembly

```asm
0x1800904d8  mov     [rsp-8+arg_18], rbx
0x1800904dd  push    rbp
0x1800904de  push    rsi
0x1800904df  push    rdi
0x1800904e0  push    r12
0x1800904e2  push    r13
0x1800904e4  push    r14
0x1800904e6  push    r15
0x1800904e8  lea     rbp, [rsp-4A0h]
0x1800904f0  sub     rsp, 5A0h
0x1800904f7  mov     rax, cs:__security_cookie
0x1800904fe  xor     rax, rsp
0x180090501  mov     [rbp+4D0h+var_40], rax
0x180090508  xor     r13d, r13d
0x18009050b  mov     rbx, r8
0x18009050e  mov     [rbp+4D0h+var_548], r13
0x180090512  mov     rdi, rdx
0x180090515  mov     [rbp+4D0h+var_550], r13
0x180090519  mov     rsi, rcx
0x18009051c  test    r8, r8
0x18009051f  jz      loc_180090B5E
0x180090525  cmp     r13w, [r8]
0x180090529  jz      loc_180090B5E
0x18009052f  lea     r12, byte_180147320
0x180090536  xor     r8d, r8d; int
0x180090539  lea     r15d, [r13+1]
0x18009053d  mov     r9, r12; char *
0x180090540  mov     edx, r15d; int
0x180090543  mov     ecx, 800h; dwBytes
0x180090548  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x18009054d  mov     r14, rax
0x180090550  test    rax, rax
0x180090553  jnz     loc_1800905DC
0x180090559  cmp     dword ptr cs:xmmword_180169738, r13d
0x180090560  mov     ebx, 8007000Eh
0x180090565  mov     [rsp+5D0h+var_558], ebx
0x180090569  mov     [rsp+5D0h+var_560], r13d
0x18009056e  jz      loc_180090C48
0x180090574  mov     rdx, 4000000000000800h; unsigned __int64
0x18009057e  test    qword ptr cs:xmmword_180169738+8, rdx
0x180090585  jz      loc_180090C48
0x18009058b  mov     rax, cs:qword_180169748
0x180090592  and     rax, rdx
0x180090595  cmp     cs:qword_180169748, rax
0x18009059c  jnz     loc_180090C48
0x1800905a2  lea     rcx, [rbp+4D0h+var_540]; unsigned __int16 *
0x1800905a6  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800905ab  lea     rcx, [rbp+4D0h+var_540]
0x1800905af  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800905b3  inc     rax
0x1800905b6  cmp     [rcx+rax*2], r13w
0x1800905bb  jnz     short loc_1800905B3
0x1800905bd  lea     ecx, [rax+rax]
0x1800905c0  add     rcx, 2
0x1800905c4  lea     rax, [rbp+4D0h+var_540]
0x1800905c8  mov     [rsp+5D0h+var_570], rcx
0x1800905cd  lea     r9, [rsp+5D0h+var_558]
0x1800905d2  lea     rcx, [rsp+5D0h+var_560]
0x1800905d7  jmp     loc_180090BF9
0x1800905dc  mov     r9, rbx
0x1800905df  mov     [rsp+5D0h+pStgOptions], rsi
0x1800905e4  lea     r8, aSSCab; "%s\\%s.cab"
0x1800905eb  mov     edx, 400h; unsigned __int64
0x1800905f0  mov     rcx, r14; unsigned __int16 *
0x1800905f3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800905f8  mov     ebx, eax
0x1800905fa  test    eax, eax
0x1800905fc  jns     short loc_180090669
0x1800905fe  cmp     dword ptr cs:xmmword_180169738, r13d
0x180090605  mov     [rsp+5D0h+var_558], r13d
0x18009060a  mov     [rsp+5D0h+var_560], eax
0x18009060e  jz      loc_180090B4E
0x180090614  mov     rdx, 4000000000000800h; unsigned __int64
0x18009061e  test    qword ptr cs:xmmword_180169738+8, rdx
0x180090625  jz      loc_180090B4E
0x18009062b  mov     rax, cs:qword_180169748
0x180090632  and     rax, rdx
0x180090635  cmp     cs:qword_180169748, rax
0x18009063c  jnz     loc_180090B4E
0x180090642  lea     rcx, [rbp+4D0h+var_4C0]; unsigned __int16 *
0x180090646  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009064b  lea     rcx, [rbp+4D0h+var_4C0]
0x18009064f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180090653  inc     rax
0x180090656  cmp     [rcx+rax*2], r13w
0x18009065b  jnz     short loc_180090653
0x18009065d  lea     ecx, [rax+rax]
0x180090660  lea     rax, [rbp+4D0h+var_4C0]
0x180090664  jmp     loc_180090AEC
0x180090669  mov     r8, r14; unsigned __int16 *
0x18009066c  mov     rcx, r14; unsigned __int16 *
0x18009066f  call    ?PlaiExpandVariables@@YAJPEAG_KPEBG@Z; PlaiExpandVariables(ushort *,unsigned __int64,ushort const *)
0x180090674  mov     ebx, eax
0x180090676  test    eax, eax
0x180090678  jns     short loc_1800906EE
0x18009067a  cmp     dword ptr cs:xmmword_180169738, r13d
0x180090681  mov     [rsp+5D0h+var_558], r13d
0x180090686  mov     [rsp+5D0h+var_560], eax
0x18009068a  jz      loc_180090B4E
0x180090690  mov     rdx, 4000000000000800h; unsigned __int64
0x18009069a  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800906a1  jz      loc_180090B4E
0x1800906a7  mov     rax, cs:qword_180169748
0x1800906ae  and     rax, rdx
0x1800906b1  cmp     cs:qword_180169748, rax
0x1800906b8  jnz     loc_180090B4E
0x1800906be  lea     rcx, [rbp+4D0h+var_440]; unsigned __int16 *
0x1800906c5  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800906ca  lea     rcx, [rbp+4D0h+var_440]
0x1800906d1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800906d5  inc     rax
0x1800906d8  cmp     [rcx+rax*2], r13w
0x1800906dd  jnz     short loc_1800906D5
0x1800906df  lea     ecx, [rax+rax]
0x1800906e2  lea     rax, [rbp+4D0h+var_440]
0x1800906e9  jmp     loc_180090AEC
0x1800906ee  xor     r9d, r9d; grfAttrs
0x1800906f1  lea     rax, [rbp+4D0h+var_550]
0x1800906f5  mov     [rsp+5D0h+ppObjectOpen], rax; ppObjectOpen
0x1800906fa  mov     rcx, rdi; pwcsName
0x1800906fd  lea     rax, IID_IPropertySetStorage
0x180090704  mov     [rsp+5D0h+riid], rax; riid
0x180090709  lea     esi, [r9+3]
0x18009070d  mov     [rsp+5D0h+pSecurityDescriptor], r13; pSecurityDescriptor
0x180090712  mov     r8d, esi; stgfmt
0x180090715  mov     [rsp+5D0h+pStgOptions], r13; pStgOptions
0x18009071a  lea     edx, [rsi+0Fh]; grfMode
0x18009071d  call    cs:__imp_StgOpenStorageEx
0x180090723  mov     ebx, eax
0x180090725  test    eax, eax
0x180090727  jns     short loc_18009079D
0x180090729  cmp     dword ptr cs:xmmword_180169738, r13d
0x180090730  mov     [rsp+5D0h+var_558], r13d
0x180090735  mov     [rsp+5D0h+var_560], eax
0x180090739  jz      loc_180090B4E
0x18009073f  mov     rdx, 4000000000000800h; unsigned __int64
0x180090749  test    qword ptr cs:xmmword_180169738+8, rdx
0x180090750  jz      loc_180090B4E
0x180090756  mov     rax, cs:qword_180169748
0x18009075d  and     rax, rdx
0x180090760  cmp     cs:qword_180169748, rax
0x180090767  jnz     loc_180090B4E
0x18009076d  lea     rcx, [rbp+4D0h+var_3C0]; unsigned __int16 *
0x180090774  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180090779  lea     rcx, [rbp+4D0h+var_3C0]
0x180090780  or      rax, 0FFFFFFFFFFFFFFFFh
0x180090784  inc     rax
0x180090787  cmp     [rcx+rax*2], r13w
0x18009078c  jnz     short loc_180090784
0x18009078e  lea     ecx, [rax+rax]
0x180090791  lea     rax, [rbp+4D0h+var_3C0]
0x180090798  jmp     loc_180090AEC
0x18009079d  mov     rcx, [rbp+4D0h+var_550]
0x1800907a1  lea     r9, [rbp+4D0h+var_548]
0x1800907a5  mov     r8d, 10h
0x1800907ab  lea     rdx, ?FMTID_PlaFileCopied@@3U_GUID@@A; _GUID FMTID_PlaFileCopied
0x1800907b2  mov     rax, [rcx]
0x1800907b5  mov     rax, [rax+20h]
0x1800907b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800907be  mov     ebx, eax
0x1800907c0  test    eax, eax
0x1800907c2  js      short loc_1800907CC
0x1800907c4  mov     ebx, r13d
0x1800907c7  jmp     loc_180090B4E
0x1800907cc  cmp     eax, 80030002h
0x1800907d1  jz      short loc_180090847
0x1800907d3  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800907da  mov     [rsp+5D0h+var_558], r13d
0x1800907df  mov     [rsp+5D0h+var_560], eax
0x1800907e3  jz      loc_180090B4E
0x1800907e9  mov     rdx, 4000000000000800h; unsigned __int64
0x1800907f3  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800907fa  jz      loc_180090B4E
0x180090800  mov     rax, cs:qword_180169748
0x180090807  and     rax, rdx
0x18009080a  cmp     cs:qword_180169748, rax
0x180090811  jnz     loc_180090B4E
0x180090817  lea     rcx, [rbp+4D0h+var_340]; unsigned __int16 *
0x18009081e  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180090823  lea     rcx, [rbp+4D0h+var_340]
0x18009082a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009082e  inc     rax
0x180090831  cmp     [rcx+rax*2], r13w
0x180090836  jnz     short loc_18009082E
0x180090838  lea     ecx, [rax+rax]
0x18009083b  lea     rax, [rbp+4D0h+var_340]
0x180090842  jmp     loc_180090AEC
0x180090847  mov     rcx, [rbp+4D0h+var_550]
0x18009084b  test    rcx, rcx
0x18009084e  jz      short loc_180090860
0x180090850  mov     rax, [rcx]
0x180090853  mov     rax, [rax+10h]
0x180090857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009085c  mov     [rbp+4D0h+var_550], r13
0x180090860  xor     r8d, r8d; bFailIfExists
0x180090863  mov     rdx, r14; lpNewFileName
0x180090866  mov     rcx, rdi; lpExistingFileName
0x180090869  call    cs:__imp_CopyFileW
0x18009086f  test    eax, eax
0x180090871  jnz     loc_18009090D
0x180090877  call    cs:__imp_GetLastError
0x18009087d  mov     ecx, eax; unsigned int
0x18009087f  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180090884  mov     ecx, 80000000h
0x180090889  mov     ebx, eax
0x18009088b  add     eax, ecx
0x18009088d  test    ecx, eax
0x18009088f  jnz     short loc_18009090D
0x180090891  cmp     ebx, 800700B7h
0x180090897  jz      short loc_18009090D
0x180090899  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800908a0  mov     [rsp+5D0h+var_558], r13d
0x1800908a5  mov     [rsp+5D0h+var_560], ebx
0x1800908a9  jz      loc_180090B4E
0x1800908af  mov     rdx, 4000000000000800h; unsigned __int64
0x1800908b9  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800908c0  jz      loc_180090B4E
0x1800908c6  mov     rax, cs:qword_180169748
0x1800908cd  and     rax, rdx
0x1800908d0  cmp     cs:qword_180169748, rax
0x1800908d7  jnz     loc_180090B4E
0x1800908dd  lea     rcx, [rbp+4D0h+var_2C0]; unsigned __int16 *
0x1800908e4  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800908e9  lea     rcx, [rbp+4D0h+var_2C0]
0x1800908f0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800908f4  inc     rax
0x1800908f7  cmp     [rcx+rax*2], r13w
0x1800908fc  jnz     short loc_1800908F4
0x1800908fe  lea     ecx, [rax+rax]
0x180090901  lea     rax, [rbp+4D0h+var_2C0]
0x180090908  jmp     loc_180090AEC
0x18009090d  lea     rax, [rbp+4D0h+var_550]
0x180090911  xor     r9d, r9d; grfAttrs
0x180090914  mov     [rsp+5D0h+ppObjectOpen], rax; ppObjectOpen
0x180090919  mov     r8d, esi; stgfmt
0x18009091c  lea     rax, IID_IPropertySetStorage
0x180090923  mov     rcx, rdi; pwcsName
0x180090926  mov     [rsp+5D0h+riid], rax; riid
0x18009092b  mov     [rsp+5D0h+pSecurityDescriptor], r13; pSecurityDescriptor
0x180090930  lea     edx, [r9+12h]; grfMode
0x180090934  mov     [rsp+5D0h+pStgOptions], r13; pStgOptions
0x180090939  call    cs:__imp_StgOpenStorageEx
0x18009093f  mov     ebx, eax
0x180090941  test    eax, eax
0x180090943  jns     short loc_1800909B9
0x180090945  cmp     dword ptr cs:xmmword_180169738, r13d
0x18009094c  mov     [rsp+5D0h+var_558], r13d
0x180090951  mov     [rsp+5D0h+var_560], eax
0x180090955  jz      loc_180090B4E
0x18009095b  mov     rdx, 4000000000000800h; unsigned __int64
0x180090965  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009096c  jz      loc_180090B4E
0x180090972  mov     rax, cs:qword_180169748
0x180090979  and     rax, rdx
0x18009097c  cmp     cs:qword_180169748, rax
0x180090983  jnz     loc_180090B4E
0x180090989  lea     rcx, [rbp+4D0h+var_240]; unsigned __int16 *
0x180090990  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180090995  lea     rcx, [rbp+4D0h+var_240]
0x18009099c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800909a0  inc     rax
0x1800909a3  cmp     [rcx+rax*2], r13w
0x1800909a8  jnz     short loc_1800909A0
0x1800909aa  lea     ecx, [rax+rax]
0x1800909ad  lea     rax, [rbp+4D0h+var_240]
0x1800909b4  jmp     loc_180090AEC
0x1800909b9  mov     rcx, [rbp+4D0h+var_550]
0x1800909bd  lea     r8, [rbp+4D0h+var_548]
0x1800909c1  mov     [rsp+5D0h+pSecurityDescriptor], r8
0x1800909c6  lea     rdx, ?FMTID_PlaFileCopied@@3U_GUID@@A; _GUID FMTID_PlaFileCopied
0x1800909cd  xor     r9d, r9d
0x1800909d0  mov     dword ptr [rsp+5D0h+pStgOptions], 1012h
0x1800909d8  xor     r8d, r8d
0x1800909db  mov     rax, [rcx]
0x1800909de  mov     rax, [rax+18h]
0x1800909e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800909e7  mov     ebx, eax
0x1800909e9  test    eax, eax
0x1800909eb  jns     short loc_180090A61
0x1800909ed  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800909f4  mov     [rsp+5D0h+var_558], r13d
0x1800909f9  mov     [rsp+5D0h+var_560], eax
0x1800909fd  jz      loc_180090B4E
0x180090a03  mov     rdx, 4000000000000800h; unsigned __int64
0x180090a0d  test    qword ptr cs:xmmword_180169738+8, rdx
0x180090a14  jz      loc_180090B4E
0x180090a1a  mov     rax, cs:qword_180169748
0x180090a21  and     rax, rdx
0x180090a24  cmp     cs:qword_180169748, rax
0x180090a2b  jnz     loc_180090B4E
0x180090a31  lea     rcx, [rbp+4D0h+var_1C0]; unsigned __int16 *
0x180090a38  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180090a3d  lea     rcx, [rbp+4D0h+var_1C0]
0x180090a44  or      rax, 0FFFFFFFFFFFFFFFFh
0x180090a48  inc     rax
0x180090a4b  cmp     [rcx+rax*2], r13w
0x180090a50  jnz     short loc_180090A48
0x180090a52  lea     ecx, [rax+rax]
0x180090a55  lea     rax, [rbp+4D0h+var_1C0]
0x180090a5c  jmp     loc_180090AEC
  ... truncated ...
```
