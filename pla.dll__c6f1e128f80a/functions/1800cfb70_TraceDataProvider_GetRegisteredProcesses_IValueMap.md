# TraceDataProvider::GetRegisteredProcesses(IValueMap * *)

- ea: `0x1800cfb70`
- end: `0x1800d059f`
- name: `?GetRegisteredProcesses@TraceDataProvider@@UEAAJPEAPEAUIValueMap@@@Z`
- size: `2607`
- prototype: `__int64 __fastcall(TraceDataProvider *__hidden this, struct IValueMap **)`
- caller_count: `0`
- callee_count: `17`
- tags: `installer_update`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180009240`
- `0x18000bf88`
- `0x1800106d0`
- `0x180010f10`
- `0x180012ef0`
- `0x180018420`
- `0x1800198b0`
- `0x18001a850`
- `0x180024ea0`
- `0x180026850`
- `0x18003f7c4`
- `0x18004e518`
- `0x1800cfb70`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d0501`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d0501`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cfbe2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cfbe2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d0054`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d0545`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d0054`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d0545`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800d0065`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800d0065`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x1800d0086`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x1800d0086`

## pseudocode

```c
__int64 __fastcall TraceDataProvider::GetRegisteredProcesses(TraceDataProvider *this, struct IValueMap **a2)
{
  struct IValueMap *v2; // r14
  HANDLE v4; // rdi
  struct _TRACE_GUID_INFO *v5; // r13
  char *v6; // r15
  LPWSTR v8; // rsi
  int v9; // ebx
  __int64 v10; // rax
  int *v11; // r9
  ValueMap *Class; // rax
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rax
  ULONG v20; // esi
  struct _TRACE_GUID_INFO *v21; // rdi
  char *v22; // rax
  int v23; // eax
  HANDLE v24; // rax
  const char *v25; // rdx
  int v26; // r8d
  OLECHAR *v27; // rax
  int v28; // eax
  HRESULT (__stdcall *Add)(IValueMap *, VARIANT); // rax
  int v30; // eax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  int v37; // eax
  __int64 v38; // rax
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+70h] [rbp-90h] BYREF
  int v42; // [rsp+78h] [rbp-88h] BYREF
  HANDLE hObject; // [rsp+80h] [rbp-80h]
  LPWSTR lpFilename; // [rsp+88h] [rbp-78h]
  struct _TRACE_GUID_INFO *v45; // [rsp+90h] [rbp-70h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp-68h]
  TraceDataProvider *v47; // [rsp+A0h] [rbp-60h]
  struct tagVARIANT v48; // [rsp+A8h] [rbp-58h] BYREF
  __int128 InBuffer; // [rsp+C0h] [rbp-40h] BYREF
  IRecordInfo *pRecInfo; // [rsp+D0h] [rbp-30h]
  unsigned __int16 v51[64]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v52[64]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v53[64]; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned __int16 v54[64]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 v55[64]; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned __int16 v56[64]; // [rsp+360h] [rbp+260h] BYREF
  unsigned __int16 v57[64]; // [rsp+3E0h] [rbp+2E0h] BYREF
  unsigned __int16 v58[64]; // [rsp+460h] [rbp+360h] BYREF
  unsigned __int16 v59[64]; // [rsp+4E0h] [rbp+3E0h] BYREF
  unsigned __int16 v60[64]; // [rsp+560h] [rbp+460h] BYREF
  unsigned __int16 v61[64]; // [rsp+5E0h] [rbp+4E0h] BYREF
  unsigned __int16 v62[64]; // [rsp+660h] [rbp+560h] BYREF

  v2 = 0;
  v47 = this;
  bstrString = 0;
  hObject = 0;
  v45 = 0;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  memset(&v48, 0, sizeof(v48));
  PlaiVariantInit(&v48);
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  lpFilename = (LPWSTR)PlaiAlloc(0x800u, 1, 0, qword_180147320, v40);
  v8 = lpFilename;
  if ( !lpFilename )
  {
    v9 = -2147024882;
    v41 = 0;
    v42 = -2147024882;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_101;
    }
    PlaiWhoAmI(v51, 0x4000000000000800uLL);
    v10 = -1;
    do
      ++v10;
    while ( v51[v10] );
    v11 = &v42;
LABEL_10:
    EventingWriteEvent((__int64)&g_Eventing, (__int64)PLA_EVENT_ERROR, 5, (__int64)v11);
    goto LABEL_101;
  }
  Class = (ValueMap *)CreateClassObject<ValueMap>();
  v2 = (struct IValueMap *)Class;
  if ( !Class )
  {
    v9 = -2147024882;
    v42 = 0;
    v41 = -2147024882;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_101;
    }
    PlaiWhoAmI(v52, 0x4000000000000800uLL);
    v13 = -1;
    do
      ++v13;
    while ( v52[v13] );
LABEL_17:
    v11 = &v41;
    goto LABEL_10;
  }
  v14 = ValueMap::put_ValueType(Class, 0x13u);
  v9 = v14;
  if ( v14 < 0 )
  {
    v41 = v14;
    v42 = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_101;
    }
    PlaiWhoAmI(v53, 0x4000000000000800uLL);
    v15 = -1;
    do
      ++v15;
    while ( v53[v15] );
    goto LABEL_17;
  }
  v16 = ((__int64 (__fastcall *)(struct IValueMap *, __int64))v2->lpVtbl->put_ValueMapType)(v2, 3);
  v9 = v16;
  if ( v16 < 0 )
  {
    v41 = v16;
    v42 = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_101;
    }
    PlaiWhoAmI(v54, 0x4000000000000800uLL);
    v17 = -1;
    do
      ++v17;
    while ( v54[v17] );
    goto LABEL_17;
  }
  PlaiSetValueMapDescription(0x25Du, v2);
  InBuffer = *((_OWORD *)v47 + 5);
  v18 = TraceSession::LoadGuidInfo(&InBuffer, &v45);
  v9 = v18;
  if ( v18 < 0 )
  {
    v41 = v18;
    v42 = 0;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v55, 0x4000000000000800uLL);
      v19 = -1;
      do
        ++v19;
      while ( v55[v19] );
      EventingWriteEvent((__int64)&g_Eventing, (__int64)PLA_EVENT_ERROR, 5, (__int64)&v41);
    }
    v5 = v45;
    goto LABEL_101;
  }
  v5 = v45;
  v20 = 0;
  v21 = v45 + 1;
  while ( 1 )
  {
    if ( v20 >= v5->InstanceCount )
    {
      v37 = ((__int64 (__fastcall *)(struct IValueMap *, GUID *, struct IValueMap **))v2->lpVtbl->QueryInterface)(
              v2,
              &IID_IValueMap,
              a2);
      v9 = v37;
      if ( v37 < 0 )
      {
        v42 = 0;
        v41 = v37;
        if ( (_DWORD)xmmword_180169738 )
        {
          if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v62, 0x4000000000000800uLL);
            v38 = -1;
            do
              ++v38;
            while ( v62[v38] );
            goto LABEL_99;
          }
        }
      }
      goto LABEL_100;
    }
    if ( v21[1].InstanceCount || (v21[1].Reserved & 2) == 0 )
      break;
LABEL_56:
    v21 = (struct _TRACE_GUID_INFO *)((char *)v21 + v21->InstanceCount);
    ++v20;
  }
  if ( v6 )
    (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
  v22 = CreateClassObject<ValueMapItem>();
  v6 = v22;
  if ( v22 )
  {
    v23 = PlaiPutUlValue<ValueMapItem>(v22, v21[1].InstanceCount);
    v9 = v23;
    if ( v23 < 0 )
    {
      v41 = v23;
      v42 = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_100;
      }
      PlaiWhoAmI(v60, 0x4000000000000800uLL);
      v35 = -1;
      do
        ++v35;
      while ( v60[v35] );
    }
    else
    {
      PlaiVariantClear(&v48);
      v9 = (**(__int64 (__fastcall ***)(char *, GUID *, ULONG *))v6)(v6, &IID_IDispatch, (ULONG *)&v48.cyVal);
      if ( v9 < 0 )
      {
        v41 = v9;
        v42 = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_100;
        }
        PlaiWhoAmI(v59, 0x4000000000000800uLL);
        v34 = -1;
        do
          ++v34;
        while ( v59[v34] );
      }
      else
      {
        if ( hObject )
          CloseHandle(hObject);
        v24 = OpenProcess(0x410u, 0, v21[1].InstanceCount);
        hObject = v24;
        if ( v24 && K32GetModuleFileNameExW(v24, 0, lpFilename, 0x400u) )
        {
          PlaiFreeString(bstrString);
          v27 = PlaiAllocStringEx(lpFilename, v25, v26);
          bstrString = v27;
          if ( !v27 )
          {
            v9 = -2147024882;
            v42 = 0;
            v41 = -2147024882;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_100;
            }
            PlaiWhoAmI(v57, 0x4000000000000800uLL);
            v32 = -1;
            do
              ++v32;
            while ( v57[v32] );
            goto LABEL_99;
          }
          v28 = (*(__int64 (__fastcall **)(char *, OLECHAR *))(*(_QWORD *)v6 + 96LL))(v6, v27);
          v9 = v28;
          if ( v28 < 0 )
          {
            v41 = v28;
            v42 = 0;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_100;
            }
            PlaiWhoAmI(v56, 0x4000000000000800uLL);
            v31 = -1;
            do
              ++v31;
            while ( v56[v31] );
            goto LABEL_99;
          }
        }
        pRecInfo = v48.pRecInfo;
        v48.vt = 9;
        Add = v2->lpVtbl->Add;
        InBuffer = *(_OWORD *)&v48.vt;
        v30 = ((__int64 (__fastcall *)(struct IValueMap *, __int128 *))Add)(v2, &InBuffer);
        v9 = v30;
        if ( v30 >= 0 )
          goto LABEL_56;
        v41 = v30;
        v42 = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_100;
        }
        PlaiWhoAmI(v58, 0x4000000000000800uLL);
        v33 = -1;
        do
          ++v33;
        while ( v58[v33] );
      }
    }
LABEL_99:
    EventingWriteEvent((__int64)&g_Eventing, (__int64)PLA_EVENT_ERROR, 5, (__int64)&v41);
    goto LABEL_100;
  }
  v9 = -2147024882;
  v42 = 0;
  v41 = -2147024882;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v61, 0x4000000000000800uLL);
    v36 = -1;
    do
      ++v36;
    while ( v61[v36] );
    goto LABEL_99;
  }
LABEL_100:
  v4 = hObject;
  v8 = lpFilename;
LABEL_101:
  if ( *((_DWORD *)v47 + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v47 + 16));
  PlaiVariantClear(&v48);
  if ( v5 )
    PlaiFree(v5, 1);
  if ( v8 )
    PlaiFree(v8, 1);
  PlaiFreeString(bstrString);
  if ( v4 )
    CloseHandle(v4);
  if ( v2 )
    ((void (__fastcall *)(struct IValueMap *))v2->lpVtbl->Release)(v2);
  if ( v6 )
    (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800cfb70  mov     [rsp-8+arg_10], rbx
0x1800cfb75  push    rbp
0x1800cfb76  push    rsi
0x1800cfb77  push    rdi
0x1800cfb78  push    r12
0x1800cfb7a  push    r13
0x1800cfb7c  push    r14
0x1800cfb7e  push    r15
0x1800cfb80  lea     rbp, [rsp-5F0h]
0x1800cfb88  sub     rsp, 6F0h
0x1800cfb8f  mov     rax, cs:__security_cookie
0x1800cfb96  xor     rax, rsp
0x1800cfb99  mov     [rbp+620h+var_40], rax
0x1800cfba0  xor     r14d, r14d
0x1800cfba3  mov     [rbp+620h+var_680], rcx
0x1800cfba7  mov     rbx, rcx
0x1800cfbaa  mov     [rbp+620h+bstrString], r14
0x1800cfbae  xorps   xmm0, xmm0
0x1800cfbb1  mov     [rbp+620h+hObject], r14
0x1800cfbb5  xor     eax, eax
0x1800cfbb7  mov     [rbp+620h+var_690], r14
0x1800cfbbb  lea     rcx, [rbp+620h+var_678]; struct tagVARIANT *
0x1800cfbbf  mov     qword ptr [rbp+620h+var_678+10h], rax
0x1800cfbc3  mov     edi, r14d
0x1800cfbc6  mov     r13d, r14d
0x1800cfbc9  mov     r15d, r14d
0x1800cfbcc  mov     r12, rdx
0x1800cfbcf  movups  xmmword ptr [rbp+620h+var_678], xmm0
0x1800cfbd3  call    ?PlaiVariantInit@@YAJPEAUtagVARIANT@@@Z; PlaiVariantInit(tagVARIANT *)
0x1800cfbd8  cmp     [rbx+8], r14d
0x1800cfbdc  jz      short loc_1800CFBE8
0x1800cfbde  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800cfbe2  call    cs:__imp_EnterCriticalSection
0x1800cfbe8  xor     r8d, r8d; int
0x1800cfbeb  lea     r9, qword_180147320; char *
0x1800cfbf2  mov     ecx, 800h; dwBytes
0x1800cfbf7  lea     edx, [r8+1]; int
0x1800cfbfb  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800cfc00  mov     [rbp+620h+lpFilename], rax
0x1800cfc04  mov     rsi, rax
0x1800cfc07  test    rax, rax
0x1800cfc0a  jnz     loc_1800CFCF2
0x1800cfc10  xor     r12d, r12d
0x1800cfc13  mov     ecx, 8007000Eh
0x1800cfc18  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800cfc1f  mov     ebx, ecx
0x1800cfc21  mov     [rsp+720h+var_6B0], r12d
0x1800cfc26  mov     [rsp+720h+var_6A8], ecx
0x1800cfc2a  jz      loc_1800D04F3
0x1800cfc30  mov     rdx, 4000000000000800h; unsigned __int64
0x1800cfc3a  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800cfc41  jz      loc_1800D04F3
0x1800cfc47  mov     rax, cs:qword_180169748
0x1800cfc4e  and     rax, rdx
0x1800cfc51  cmp     cs:qword_180169748, rax
0x1800cfc58  jnz     loc_1800D04F3
0x1800cfc5e  lea     rcx, [rbp+620h+var_640]; unsigned __int16 *
0x1800cfc62  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800cfc67  lea     rcx, [rbp+620h+var_640]
0x1800cfc6b  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800cfc6f  inc     rax
0x1800cfc72  cmp     [rcx+rax*2], r12w
0x1800cfc77  jnz     short loc_1800CFC6F
0x1800cfc79  lea     ecx, [rax+rax]
0x1800cfc7c  add     rcx, 2
0x1800cfc80  lea     rax, [rbp+620h+var_640]
0x1800cfc84  mov     [rsp+720h+var_6C0], rcx
0x1800cfc89  lea     r9, [rsp+720h+var_6A8]
0x1800cfc8e  lea     rcx, [rsp+720h+var_6B0]
0x1800cfc93  mov     [rsp+720h+var_6C8], rax
0x1800cfc98  lea     rdx, PLA_EVENT_ERROR
0x1800cfc9f  mov     [rsp+720h+var_6D0], 2Ah ; '*'
0x1800cfca8  lea     rax, aTracedataprovi_8; "TraceDataProvider::GetRegisteredProcess"...
0x1800cfcaf  mov     [rsp+720h+var_6D8], rax
0x1800cfcb4  mov     eax, 4
0x1800cfcb9  mov     [rsp+720h+var_6E0], rax
0x1800cfcbe  mov     [rsp+720h+var_6E8], rcx
0x1800cfcc3  lea     rcx, qword_180147320
0x1800cfcca  mov     [rsp+720h+var_6F0], 1
0x1800cfcd3  mov     [rsp+720h+var_6F8], rcx
0x1800cfcd8  lea     r8d, [rax+1]
0x1800cfcdc  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800cfce3  mov     [rsp+720h+var_700], rax
0x1800cfce8  call    EventingWriteEvent
0x1800cfced  jmp     loc_1800D04F3
0x1800cfcf2  call    ??$CreateClassObject@VValueMap@@@@YAPEAVValueMap@@PEBDH@Z; CreateClassObject<ValueMap>(char const *,int)
0x1800cfcf7  mov     r14, rax
0x1800cfcfa  test    rax, rax
0x1800cfcfd  jnz     loc_1800CFD8B
0x1800cfd03  xor     r12d, r12d
0x1800cfd06  mov     ecx, 8007000Eh
0x1800cfd0b  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800cfd12  mov     ebx, ecx
0x1800cfd14  mov     [rsp+720h+var_6A8], r12d
0x1800cfd19  mov     [rsp+720h+var_6B0], ecx
0x1800cfd1d  jz      loc_1800D04F3
0x1800cfd23  mov     rdx, 4000000000000800h; unsigned __int64
0x1800cfd2d  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800cfd34  jz      loc_1800D04F3
0x1800cfd3a  mov     rax, cs:qword_180169748
0x1800cfd41  and     rax, rdx
0x1800cfd44  cmp     cs:qword_180169748, rax
0x1800cfd4b  jnz     loc_1800D04F3
0x1800cfd51  lea     rcx, [rbp+620h+var_5C0]; unsigned __int16 *
0x1800cfd55  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800cfd5a  lea     rcx, [rbp+620h+var_5C0]
0x1800cfd5e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800cfd62  inc     rax
0x1800cfd65  cmp     [rcx+rax*2], r12w
0x1800cfd6a  jnz     short loc_1800CFD62
0x1800cfd6c  lea     ecx, [rax+rax]
0x1800cfd6f  lea     rax, [rbp+620h+var_5C0]
0x1800cfd73  add     rcx, 2
0x1800cfd77  lea     r9, [rsp+720h+var_6B0]
0x1800cfd7c  mov     [rsp+720h+var_6C0], rcx
0x1800cfd81  lea     rcx, [rsp+720h+var_6A8]
0x1800cfd86  jmp     loc_1800CFC93
0x1800cfd8b  mov     edx, 13h; unsigned __int16
0x1800cfd90  mov     rcx, r14; this
0x1800cfd93  call    ?put_ValueType@ValueMap@@QEAAJG@Z; ValueMap::put_ValueType(ushort)
0x1800cfd98  mov     ebx, eax
0x1800cfd9a  test    eax, eax
0x1800cfd9c  jns     short loc_1800CFE15
0x1800cfd9e  xor     r12d, r12d
0x1800cfda1  mov     [rsp+720h+var_6B0], eax
0x1800cfda5  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800cfdac  mov     [rsp+720h+var_6A8], r12d
0x1800cfdb1  jz      loc_1800D04F3
0x1800cfdb7  mov     rdx, 4000000000000800h; unsigned __int64
0x1800cfdc1  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800cfdc8  jz      loc_1800D04F3
0x1800cfdce  mov     rax, cs:qword_180169748
0x1800cfdd5  and     rax, rdx
0x1800cfdd8  cmp     cs:qword_180169748, rax
0x1800cfddf  jnz     loc_1800D04F3
0x1800cfde5  lea     rcx, [rbp+620h+var_540]; unsigned __int16 *
0x1800cfdec  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800cfdf1  lea     rcx, [rbp+620h+var_540]
0x1800cfdf8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800cfdfc  inc     rax
0x1800cfdff  cmp     [rcx+rax*2], r12w
0x1800cfe04  jnz     short loc_1800CFDFC
0x1800cfe06  lea     ecx, [rax+rax]
0x1800cfe09  lea     rax, [rbp+620h+var_540]
0x1800cfe10  jmp     loc_1800CFD73
0x1800cfe15  mov     rax, [r14]
0x1800cfe18  mov     edx, 3
0x1800cfe1d  mov     rcx, r14
0x1800cfe20  mov     rax, [rax+78h]
0x1800cfe24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cfe29  mov     ebx, eax
0x1800cfe2b  test    eax, eax
0x1800cfe2d  jns     short loc_1800CFEA6
0x1800cfe2f  xor     r12d, r12d
0x1800cfe32  mov     [rsp+720h+var_6B0], eax
0x1800cfe36  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800cfe3d  mov     [rsp+720h+var_6A8], r12d
0x1800cfe42  jz      loc_1800D04F3
0x1800cfe48  mov     rdx, 4000000000000800h; unsigned __int64
0x1800cfe52  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800cfe59  jz      loc_1800D04F3
0x1800cfe5f  mov     rax, cs:qword_180169748
0x1800cfe66  and     rax, rdx
0x1800cfe69  cmp     cs:qword_180169748, rax
0x1800cfe70  jnz     loc_1800D04F3
0x1800cfe76  lea     rcx, [rbp+620h+var_4C0]; unsigned __int16 *
0x1800cfe7d  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800cfe82  lea     rcx, [rbp+620h+var_4C0]
0x1800cfe89  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800cfe8d  inc     rax
0x1800cfe90  cmp     [rcx+rax*2], r12w
0x1800cfe95  jnz     short loc_1800CFE8D
0x1800cfe97  lea     ecx, [rax+rax]
0x1800cfe9a  lea     rax, [rbp+620h+var_4C0]
0x1800cfea1  jmp     loc_1800CFD73
0x1800cfea6  mov     rdx, r14; struct IValueMap *
0x1800cfea9  mov     ecx, 25Dh; uID
0x1800cfeae  call    ?PlaiSetValueMapDescription@@YAJIPEAUIValueMap@@@Z; PlaiSetValueMapDescription(uint,IValueMap *)
0x1800cfeb3  mov     rax, [rbp+620h+var_680]
0x1800cfeb7  lea     rdx, [rbp+620h+var_690]; struct _TRACE_GUID_INFO **
0x1800cfebb  lea     rcx, [rbp+620h+InBuffer]; InBuffer
0x1800cfebf  movups  xmm0, xmmword ptr [rax+50h]
0x1800cfec3  movdqu  [rbp+620h+InBuffer], xmm0
0x1800cfec8  call    ?LoadGuidInfo@TraceSession@@SAJU_GUID@@PEAPEAU_TRACE_GUID_INFO@@@Z; TraceSession::LoadGuidInfo(_GUID,_TRACE_GUID_INFO * *)
0x1800cfecd  xor     ecx, ecx
0x1800cfecf  mov     ebx, eax
0x1800cfed1  test    eax, eax
0x1800cfed3  jns     loc_1800CFFC1
0x1800cfed9  xor     r12d, r12d
0x1800cfedc  mov     [rsp+720h+var_6B0], eax
0x1800cfee0  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800cfee7  mov     [rsp+720h+var_6A8], r12d
0x1800cfeec  jz      loc_1800CFFB8
0x1800cfef2  mov     rdx, 4000000000000800h; unsigned __int64
0x1800cfefc  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800cff03  jz      loc_1800CFFB8
0x1800cff09  mov     rax, cs:qword_180169748
0x1800cff10  and     rax, rdx
0x1800cff13  cmp     cs:qword_180169748, rax
0x1800cff1a  jnz     loc_1800CFFB8
0x1800cff20  lea     rcx, [rbp+620h+var_440]; unsigned __int16 *
0x1800cff27  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800cff2c  lea     rcx, [rbp+620h+var_440]
0x1800cff33  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800cff37  inc     rax
0x1800cff3a  cmp     [rcx+rax*2], r12w
0x1800cff3f  jnz     short loc_1800CFF37
0x1800cff41  lea     ecx, [rax+rax]
0x1800cff44  add     rcx, 2
0x1800cff48  lea     rax, [rbp+620h+var_440]
0x1800cff4f  mov     [rsp+720h+var_6C0], rcx
0x1800cff54  lea     r9, [rsp+720h+var_6B0]
0x1800cff59  mov     [rsp+720h+var_6C8], rax
0x1800cff5e  lea     rcx, [rsp+720h+var_6A8]
0x1800cff63  mov     [rsp+720h+var_6D0], 2Ah ; '*'
0x1800cff6c  lea     rax, aTracedataprovi_8; "TraceDataProvider::GetRegisteredProcess"...
0x1800cff73  mov     [rsp+720h+var_6D8], rax
0x1800cff78  lea     rdx, PLA_EVENT_ERROR
0x1800cff7f  mov     eax, 4
0x1800cff84  mov     [rsp+720h+var_6E0], rax
0x1800cff89  mov     [rsp+720h+var_6E8], rcx
0x1800cff8e  lea     rcx, qword_180147320
0x1800cff95  mov     [rsp+720h+var_6F0], 1
0x1800cff9e  mov     [rsp+720h+var_6F8], rcx
0x1800cffa3  lea     r8d, [rax+1]
0x1800cffa7  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800cffae  mov     [rsp+720h+var_700], rax
0x1800cffb3  call    EventingWriteEvent
0x1800cffb8  mov     r13, [rbp+620h+var_690]
0x1800cffbc  jmp     loc_1800D04F3
0x1800cffc1  mov     r13, [rbp+620h+var_690]
0x1800cffc5  mov     esi, ecx
0x1800cffc7  lea     rdi, [r13+8]
0x1800cffcb  cmp     esi, [r13+0]
0x1800cffcf  jnb     loc_1800D03EA
0x1800cffd5  cmp     [rdi+8], ecx
0x1800cffd8  jnz     short loc_1800CFFE5
0x1800cffda  mov     eax, [rdi+0Ch]
0x1800cffdd  test    al, 2
0x1800cffdf  jnz     loc_1800D0106
0x1800cffe5  test    r15, r15
0x1800cffe8  jz      short loc_1800CFFF9
0x1800cffea  mov     rax, [r15]
0x1800cffed  mov     rcx, r15
0x1800cfff0  mov     rax, [rax+10h]
0x1800cfff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cfff9  call    ??$CreateClassObject@VValueMapItem@@@@YAPEAVValueMapItem@@PEBDH@Z; CreateClassObject<ValueMapItem>(char const *,int)
0x1800cfffe  mov     r15, rax
0x1800d0001  test    rax, rax
0x1800d0004  jz      loc_1800D036C
0x1800d000a  mov     edx, [rdi+8]
0x1800d000d  mov     rcx, rax
0x1800d0010  call    ??$PlaiPutUlValue@VValueMapItem@@@@YAJPEAVValueMapItem@@K@Z; PlaiPutUlValue<ValueMapItem>(ValueMapItem *,ulong)
0x1800d0015  mov     ebx, eax
0x1800d0017  test    eax, eax
0x1800d0019  js      loc_1800D02F5
0x1800d001f  lea     rcx, [rbp+620h+var_678]; struct tagVARIANT *
0x1800d0023  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x1800d0028  mov     rax, [r15]
0x1800d002b  lea     r8, [rbp+620h+var_678+8]
0x1800d002f  lea     rdx, IID_IDispatch
0x1800d0036  mov     rcx, r15
0x1800d0039  mov     rax, [rax]
0x1800d003c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0041  mov     ebx, eax
0x1800d0043  test    eax, eax
0x1800d0045  js      loc_1800D027E
0x1800d004b  mov     rcx, [rbp+620h+hObject]; hObject
0x1800d004f  test    rcx, rcx
0x1800d0052  jz      short loc_1800D005A
0x1800d0054  call    cs:__imp_CloseHandle
0x1800d005a  mov     r8d, [rdi+8]; dwProcessId
0x1800d005e  xor     edx, edx; bInheritHandle
0x1800d0060  mov     ecx, 410h; dwDesiredAccess
0x1800d0065  call    cs:__imp_OpenProcess
0x1800d006b  mov     [rbp+620h+hObject], rax
0x1800d006f  test    rax, rax
0x1800d0072  jz      short loc_1800D00C9
0x1800d0074  mov     rbx, [rbp+620h+lpFilename]
0x1800d0078  mov     r9d, 400h; nSize
0x1800d007e  mov     r8, rbx; lpFilename
0x1800d0081  xor     edx, edx; hModule
0x1800d0083  mov     rcx, rax; hProcess
0x1800d0086  call    cs:__imp_K32GetModuleFileNameExW
0x1800d008c  test    eax, eax
0x1800d008e  jz      short loc_1800D00C9
0x1800d0090  mov     rcx, [rbp+620h+bstrString]; bstrString
0x1800d0094  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x1800d0099  mov     rcx, rbx; unsigned __int16 *
0x1800d009c  call    ?PlaiAllocStringEx@@YAPEAGPEBGPEBDH@Z; PlaiAllocStringEx(ushort const *,char const *,int)
0x1800d00a1  mov     [rbp+620h+bstrString], rax
0x1800d00a5  mov     rcx, rax
0x1800d00a8  test    rax, rax
0x1800d00ab  jz      loc_1800D0189
0x1800d00b1  mov     rax, [r15]
0x1800d00b4  mov     rdx, rcx
0x1800d00b7  mov     rcx, r15
0x1800d00ba  mov     rax, [rax+60h]
0x1800d00be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d00c3  mov     ebx, eax
  ... truncated ...
```
