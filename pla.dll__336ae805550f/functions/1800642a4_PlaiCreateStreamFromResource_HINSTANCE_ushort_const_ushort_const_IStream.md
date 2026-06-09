# PlaiCreateStreamFromResource(HINSTANCE__ *,ushort const *,ushort const *,IStream * *)

- ea: `0x1800642a4`
- end: `0x18006483a`
- name: `?PlaiCreateStreamFromResource@@YAJPEAUHINSTANCE__@@PEBG1PEAPEAUIStream@@@Z`
- size: `1430`
- prototype: `__int64 __fastcall(HINSTANCE hModule, const unsigned __int16 *, const unsigned __int16 *, struct IStream **)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800771e0`
- `0x1800eb4b8`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18002b3a0`
- `0x1800642a4`
- `0x18013ae82`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800643dc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800643dc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeResource` at `0x1800647ef`
- `api-ms-win-core-libraryloader-l1-2-0!FreeResource` at `0x1800647ef`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180064481`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180064481`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18006450e`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18006450e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800642ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800643ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006451c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800645c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006465e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800642ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800643ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006451c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800645c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006465e`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800646fd`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800646fd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006480f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006480f`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800645b1`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800645b1`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x1800642dd`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x1800642dd`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800647fd`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800647fd`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18006464c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18006464c`

## string_xrefs

- `0x18006438c`: `PlaiCreateStreamFromResource`
- `0x1800647a7`: `PlaiCreateStreamFromResource`

## pseudocode

```c
__int64 __fastcall PlaiCreateStreamFromResource(
        HINSTANCE hModule,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IStream **a4)
{
  void *v5; // rdi
  HRSRC ResourceW; // rax
  HRSRC v8; // rsi
  DWORD LastError; // eax
  signed int v10; // ebx
  __int64 v11; // rax
  int *v12; // r9
  int *v13; // rcx
  HGLOBAL Resource; // rax
  void *v15; // r12
  DWORD v16; // eax
  __int64 v17; // rax
  void *v18; // r15
  const void *v19; // r14
  __int64 v20; // rax
  DWORD v21; // eax
  signed int v22; // eax
  __int64 v23; // rax
  size_t v24; // rbx
  HGLOBAL v25; // rax
  DWORD v26; // eax
  __int64 v27; // rax
  void *v28; // rax
  DWORD v29; // eax
  __int64 v30; // rax
  HRESULT StreamOnHGlobal; // eax
  __int64 v32; // rax
  int v34; // [rsp+70h] [rbp-90h] BYREF
  signed int v35; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v36[64]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v37[64]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v38[64]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 v39[64]; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int16 v40[64]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v41[64]; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int16 v42[64]; // [rsp+380h] [rbp+280h] BYREF

  v5 = 0;
  ResourceW = FindResourceW(hModule, a2, a3);
  v8 = ResourceW;
  if ( !ResourceW )
  {
    LastError = GetLastError();
    v10 = PlaiHResultFromWin32(LastError);
    v34 = 0;
    v35 = v10;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v36, 0x4000000000000800uLL);
      v11 = -1;
      do
        ++v11;
      while ( v36[v11] );
      v12 = &v35;
      v13 = &v34;
LABEL_8:
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v12, 4, byte_180147320, 1, v13, 4);
      goto LABEL_55;
    }
    goto LABEL_55;
  }
  Resource = LoadResource(hModule, ResourceW);
  v15 = Resource;
  if ( Resource )
  {
    v18 = 0;
    v19 = LockResource(Resource);
    if ( v19 )
    {
      v21 = SizeofResource(hModule, v8);
      if ( !v21 )
      {
        v22 = GetLastError();
        v10 = v22;
        if ( v22 > 0 )
          v10 = (unsigned __int16)v22 | 0x80070000;
        v35 = 0;
        v34 = v10;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_53;
        }
        PlaiWhoAmI(v39, 0x4000000000000800uLL);
        v23 = -1;
        do
          ++v23;
        while ( v39[v23] );
        goto LABEL_52;
      }
      v24 = v21;
      v25 = GlobalAlloc(2u, v21);
      v5 = v25;
      if ( v25 )
      {
        v28 = GlobalLock(v25);
        v18 = v28;
        if ( v28 )
        {
          memcpy_0(v28, v19, v24);
          StreamOnHGlobal = CreateStreamOnHGlobal(v5, 1, a4);
          v10 = StreamOnHGlobal;
          if ( StreamOnHGlobal < 0 )
          {
            v35 = 0;
            v34 = StreamOnHGlobal;
            if ( (_DWORD)xmmword_180169738 )
            {
              if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
              {
                PlaiWhoAmI(v42, 0x4000000000000800uLL);
                v32 = -1;
                do
                  ++v32;
                while ( v42[v32] );
                goto LABEL_52;
              }
            }
          }
        }
        else
        {
          v29 = GetLastError();
          v34 = PlaiHResultFromWin32(v29);
          v10 = v34;
          v35 = 0;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v41, 0x4000000000000800uLL);
            v30 = -1;
            do
              ++v30;
            while ( v41[v30] );
            goto LABEL_52;
          }
        }
      }
      else
      {
        v26 = GetLastError();
        v34 = PlaiHResultFromWin32(v26);
        v10 = v34;
        v35 = 0;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v40, 0x4000000000000800uLL);
          v27 = -1;
          do
            ++v27;
          while ( v40[v27] );
          goto LABEL_52;
        }
      }
    }
    else
    {
      v10 = -2147467259;
      v34 = -2147467259;
      v35 = 0;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v38, 0x4000000000000800uLL);
        v20 = -1;
        do
          ++v20;
        while ( v38[v20] );
LABEL_52:
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v34, 4, byte_180147320, 1, &v35, 4);
      }
    }
LABEL_53:
    FreeResource(v15);
    if ( v18 )
      GlobalUnlock(v5);
    goto LABEL_55;
  }
  v16 = GetLastError();
  v10 = PlaiHResultFromWin32(v16);
  v35 = 0;
  v34 = v10;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v37, 0x4000000000000800uLL);
    v17 = -1;
    do
      ++v17;
    while ( v37[v17] );
    v12 = &v34;
    v13 = &v35;
    goto LABEL_8;
  }
LABEL_55:
  if ( v10 < 0 && v5 )
    GlobalFree(v5);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800642a4  push    rbp
0x1800642a6  push    rbx
0x1800642a7  push    rsi
0x1800642a8  push    rdi
0x1800642a9  push    r12
0x1800642ab  push    r13
0x1800642ad  push    r14
0x1800642af  push    r15
0x1800642b1  lea     rbp, [rsp-318h]
0x1800642b9  sub     rsp, 418h
0x1800642c0  mov     rax, cs:__security_cookie
0x1800642c7  xor     rax, rsp
0x1800642ca  mov     [rbp+350h+var_50], rax
0x1800642d1  xor     r14d, r14d
0x1800642d4  mov     r13, r9
0x1800642d7  mov     edi, r14d
0x1800642da  mov     rbx, rcx
0x1800642dd  call    cs:__imp_FindResourceW
0x1800642e3  mov     rsi, rax
0x1800642e6  test    rax, rax
0x1800642e9  jnz     loc_1800643D6
0x1800642ef  call    cs:__imp_GetLastError
0x1800642f5  mov     ecx, eax; unsigned int
0x1800642f7  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800642fc  cmp     dword ptr cs:xmmword_180169738, r14d
0x180064303  mov     ebx, eax
0x180064305  mov     [rsp+450h+var_3E0], r14d
0x18006430a  mov     [rsp+450h+var_3D8], eax
0x18006430e  jz      loc_180064803
0x180064314  mov     rdx, 4000000000000800h; unsigned __int64
0x18006431e  test    qword ptr cs:xmmword_180169738+8, rdx
0x180064325  jz      loc_180064803
0x18006432b  mov     rax, cs:qword_180169748
0x180064332  and     rax, rdx
0x180064335  cmp     cs:qword_180169748, rax
0x18006433c  jnz     loc_180064803
0x180064342  lea     rcx, [rbp+350h+var_3D0]; unsigned __int16 *
0x180064346  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18006434b  lea     rcx, [rbp+350h+var_3D0]
0x18006434f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180064353  inc     rax
0x180064356  cmp     [rcx+rax*2], r14w
0x18006435b  jnz     short loc_180064353
0x18006435d  lea     ecx, [rax+rax]
0x180064360  add     rcx, 2
0x180064364  lea     rax, [rbp+350h+var_3D0]
0x180064368  mov     [rsp+450h+var_3F0], rcx
0x18006436d  lea     r9, [rsp+450h+var_3D8]
0x180064372  lea     rcx, [rsp+450h+var_3E0]
0x180064377  mov     [rsp+450h+var_3F8], rax
0x18006437c  lea     rdx, PLA_EVENT_ERROR
0x180064383  mov     [rsp+450h+var_400], 1Dh
0x18006438c  lea     rax, aPlaicreatestre; "PlaiCreateStreamFromResource"
0x180064393  mov     [rsp+450h+var_408], rax
0x180064398  mov     eax, 4
0x18006439d  mov     [rsp+450h+var_410], rax
0x1800643a2  mov     [rsp+450h+var_418], rcx
0x1800643a7  lea     rcx, byte_180147320
0x1800643ae  mov     [rsp+450h+var_420], 1
0x1800643b7  mov     [rsp+450h+var_428], rcx
0x1800643bc  lea     r8d, [rax+1]
0x1800643c0  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800643c7  mov     [rsp+450h+var_430], rax
0x1800643cc  call    EventingWriteEvent
0x1800643d1  jmp     loc_180064803
0x1800643d6  mov     rdx, rsi; hResInfo
0x1800643d9  mov     rcx, rbx; hModule
0x1800643dc  call    cs:__imp_LoadResource
0x1800643e2  mov     r12, rax
0x1800643e5  test    rax, rax
0x1800643e8  jnz     loc_18006447B
0x1800643ee  call    cs:__imp_GetLastError
0x1800643f4  mov     ecx, eax; unsigned int
0x1800643f6  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800643fb  cmp     dword ptr cs:xmmword_180169738, r14d
0x180064402  mov     ebx, eax
0x180064404  mov     [rsp+450h+var_3D8], r14d
0x180064409  mov     [rsp+450h+var_3E0], eax
0x18006440d  jz      loc_180064803
0x180064413  mov     rdx, 4000000000000800h; unsigned __int64
0x18006441d  test    qword ptr cs:xmmword_180169738+8, rdx
0x180064424  jz      loc_180064803
0x18006442a  mov     rax, cs:qword_180169748
0x180064431  and     rax, rdx
0x180064434  cmp     cs:qword_180169748, rax
0x18006443b  jnz     loc_180064803
0x180064441  lea     rcx, [rbp+350h+var_350]; unsigned __int16 *
0x180064445  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18006444a  lea     rcx, [rbp+350h+var_350]
0x18006444e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180064452  inc     rax
0x180064455  cmp     [rcx+rax*2], r14w
0x18006445a  jnz     short loc_180064452
0x18006445c  lea     ecx, [rax+rax]
0x18006445f  add     rcx, 2
0x180064463  lea     rax, [rbp+350h+var_350]
0x180064467  mov     [rsp+450h+var_3F0], rcx
0x18006446c  lea     r9, [rsp+450h+var_3E0]
0x180064471  lea     rcx, [rsp+450h+var_3D8]
0x180064476  jmp     loc_180064377
0x18006447b  mov     rcx, r12; hResData
0x18006447e  mov     r15, r14
0x180064481  call    cs:__imp_LockResource
0x180064487  mov     r14, rax
0x18006448a  test    rax, rax
0x18006448d  jnz     short loc_180064508
0x18006448f  cmp     dword ptr cs:xmmword_180169738, r14d
0x180064496  mov     ebx, 80004005h
0x18006449b  mov     [rsp+450h+var_3E0], ebx
0x18006449f  mov     [rsp+450h+var_3D8], r14d
0x1800644a4  jz      loc_1800647EC
0x1800644aa  mov     rdx, 4000000000000800h; unsigned __int64
0x1800644b4  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800644bb  jz      loc_1800647EC
0x1800644c1  mov     rax, cs:qword_180169748
0x1800644c8  and     rax, rdx
0x1800644cb  cmp     cs:qword_180169748, rax
0x1800644d2  jnz     loc_1800647EC
0x1800644d8  lea     rcx, [rbp+350h+var_2D0]; unsigned __int16 *
0x1800644df  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800644e4  lea     rcx, [rbp+350h+var_2D0]
0x1800644eb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800644ef  inc     rax
0x1800644f2  cmp     [rcx+rax*2], r14w
0x1800644f7  jnz     short loc_1800644EF
0x1800644f9  lea     ecx, [rax+rax]
0x1800644fc  lea     rax, [rbp+350h+var_2D0]
0x180064503  jmp     loc_18006477F
0x180064508  mov     rdx, rsi; hResInfo
0x18006450b  mov     rcx, rbx; hModule
0x18006450e  call    cs:__imp_SizeofResource
0x180064514  test    eax, eax
0x180064516  jnz     loc_1800645A8
0x18006451c  call    cs:__imp_GetLastError
0x180064522  xor     r14d, r14d
0x180064525  mov     ebx, eax
0x180064527  test    eax, eax
0x180064529  jle     short loc_180064534
0x18006452b  movzx   ebx, ax
0x18006452e  or      ebx, 80070000h
0x180064534  cmp     dword ptr cs:xmmword_180169738, r14d
0x18006453b  mov     [rsp+450h+var_3D8], r14d
0x180064540  mov     [rsp+450h+var_3E0], ebx
0x180064544  jz      loc_1800647EC
0x18006454a  mov     rdx, 4000000000000800h; unsigned __int64
0x180064554  test    qword ptr cs:xmmword_180169738+8, rdx
0x18006455b  jz      loc_1800647EC
0x180064561  mov     rax, cs:qword_180169748
0x180064568  and     rax, rdx
0x18006456b  cmp     cs:qword_180169748, rax
0x180064572  jnz     loc_1800647EC
0x180064578  lea     rcx, [rbp+350h+var_250]; unsigned __int16 *
0x18006457f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180064584  lea     rcx, [rbp+350h+var_250]
0x18006458b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006458f  inc     rax
0x180064592  cmp     [rcx+rax*2], r14w
0x180064597  jnz     short loc_18006458F
0x180064599  lea     ecx, [rax+rax]
0x18006459c  lea     rax, [rbp+350h+var_250]
0x1800645a3  jmp     loc_18006477F
0x1800645a8  mov     edx, eax; dwBytes
0x1800645aa  mov     ecx, 2; uFlags
0x1800645af  mov     ebx, eax
0x1800645b1  call    cs:__imp_GlobalAlloc
0x1800645b7  mov     rdi, rax
0x1800645ba  test    rax, rax
0x1800645bd  jnz     loc_180064649
0x1800645c3  call    cs:__imp_GetLastError
0x1800645c9  mov     ecx, eax; unsigned int
0x1800645cb  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800645d0  xor     r14d, r14d
0x1800645d3  mov     [rsp+450h+var_3E0], eax
0x1800645d7  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800645de  mov     ebx, eax
0x1800645e0  mov     [rsp+450h+var_3D8], r14d
0x1800645e5  jz      loc_1800647EC
0x1800645eb  mov     rdx, 4000000000000800h; unsigned __int64
0x1800645f5  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800645fc  jz      loc_1800647EC
0x180064602  mov     rax, cs:qword_180169748
0x180064609  and     rax, rdx
0x18006460c  cmp     cs:qword_180169748, rax
0x180064613  jnz     loc_1800647EC
0x180064619  lea     rcx, [rbp+350h+var_1D0]; unsigned __int16 *
0x180064620  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180064625  lea     rcx, [rbp+350h+var_1D0]
0x18006462c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180064630  inc     rax
0x180064633  cmp     [rcx+rax*2], r14w
0x180064638  jnz     short loc_180064630
0x18006463a  lea     ecx, [rax+rax]
0x18006463d  lea     rax, [rbp+350h+var_1D0]
0x180064644  jmp     loc_18006477F
0x180064649  mov     rcx, rdi; hMem
0x18006464c  call    cs:__imp_GlobalLock
0x180064652  mov     r15, rax
0x180064655  test    rax, rax
0x180064658  jnz     loc_1800646E4
0x18006465e  call    cs:__imp_GetLastError
0x180064664  mov     ecx, eax; unsigned int
0x180064666  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18006466b  xor     r14d, r14d
0x18006466e  mov     [rsp+450h+var_3E0], eax
0x180064672  cmp     dword ptr cs:xmmword_180169738, r14d
0x180064679  mov     ebx, eax
0x18006467b  mov     [rsp+450h+var_3D8], r14d
0x180064680  jz      loc_1800647EC
0x180064686  mov     rdx, 4000000000000800h; unsigned __int64
0x180064690  test    qword ptr cs:xmmword_180169738+8, rdx
0x180064697  jz      loc_1800647EC
0x18006469d  mov     rax, cs:qword_180169748
0x1800646a4  and     rax, rdx
0x1800646a7  cmp     cs:qword_180169748, rax
0x1800646ae  jnz     loc_1800647EC
0x1800646b4  lea     rcx, [rbp+350h+var_150]; unsigned __int16 *
0x1800646bb  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800646c0  lea     rcx, [rbp+350h+var_150]
0x1800646c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800646cb  inc     rax
0x1800646ce  cmp     [rcx+rax*2], r14w
0x1800646d3  jnz     short loc_1800646CB
0x1800646d5  lea     ecx, [rax+rax]
0x1800646d8  lea     rax, [rbp+350h+var_150]
0x1800646df  jmp     loc_18006477F
0x1800646e4  mov     r8, rbx; Size
0x1800646e7  mov     rdx, r14; Src
0x1800646ea  mov     rcx, rax; void *
0x1800646ed  call    memcpy_0
0x1800646f2  mov     r8, r13; ppstm
0x1800646f5  mov     edx, 1; fDeleteOnRelease
0x1800646fa  mov     rcx, rdi; hGlobal
0x1800646fd  call    cs:__imp_CreateStreamOnHGlobal
0x180064703  xor     r14d, r14d
0x180064706  mov     ebx, eax
0x180064708  test    eax, eax
0x18006470a  jns     loc_1800647EC
0x180064710  cmp     dword ptr cs:xmmword_180169738, r14d
0x180064717  mov     [rsp+450h+var_3D8], r14d
0x18006471c  mov     [rsp+450h+var_3E0], eax
0x180064720  jz      loc_1800647EC
0x180064726  mov     rdx, 4000000000000800h; unsigned __int64
0x180064730  test    qword ptr cs:xmmword_180169738+8, rdx
0x180064737  jz      loc_1800647EC
0x18006473d  mov     rax, cs:qword_180169748
0x180064744  and     rax, rdx
0x180064747  cmp     cs:qword_180169748, rax
0x18006474e  jnz     loc_1800647EC
0x180064754  lea     rcx, [rbp+350h+var_D0]; unsigned __int16 *
0x18006475b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180064760  lea     rcx, [rbp+350h+var_D0]
0x180064767  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006476b  inc     rax
0x18006476e  cmp     [rcx+rax*2], r14w
0x180064773  jnz     short loc_18006476B
0x180064775  lea     ecx, [rax+rax]
0x180064778  lea     rax, [rbp+350h+var_D0]
0x18006477f  add     rcx, 2
0x180064783  lea     r9, [rsp+450h+var_3E0]
0x180064788  mov     [rsp+450h+var_3F0], rcx
0x18006478d  lea     rdx, PLA_EVENT_ERROR
0x180064794  mov     [rsp+450h+var_3F8], rax
0x180064799  lea     rcx, [rsp+450h+var_3D8]
0x18006479e  mov     [rsp+450h+var_400], 1Dh
0x1800647a7  lea     rax, aPlaicreatestre; "PlaiCreateStreamFromResource"
0x1800647ae  mov     [rsp+450h+var_408], rax
0x1800647b3  mov     eax, 4
0x1800647b8  mov     [rsp+450h+var_410], rax
0x1800647bd  mov     [rsp+450h+var_418], rcx
0x1800647c2  lea     rcx, byte_180147320
0x1800647c9  mov     [rsp+450h+var_420], 1
0x1800647d2  mov     [rsp+450h+var_428], rcx
0x1800647d7  lea     r8d, [rax+1]
0x1800647db  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800647e2  mov     [rsp+450h+var_430], rax
0x1800647e7  call    EventingWriteEvent
0x1800647ec  mov     rcx, r12; hResData
0x1800647ef  call    cs:__imp_FreeResource
0x1800647f5  test    r15, r15
0x1800647f8  jz      short loc_180064803
0x1800647fa  mov     rcx, rdi; hMem
0x1800647fd  call    cs:__imp_GlobalUnlock
0x180064803  test    ebx, ebx
0x180064805  jns     short loc_180064815
0x180064807  test    rdi, rdi
0x18006480a  jz      short loc_180064815
0x18006480c  mov     rcx, rdi; hMem
0x18006480f  call    cs:__imp_GlobalFree
0x180064815  mov     eax, ebx
0x180064817  mov     rcx, [rbp+350h+var_50]
0x18006481e  xor     rcx, rsp; StackCookie
0x180064821  call    __security_check_cookie
0x180064826  add     rsp, 418h
0x18006482d  pop     r15
0x18006482f  pop     r14
0x180064831  pop     r13
0x180064833  pop     r12
0x180064835  pop     rdi
0x180064836  pop     rsi
0x180064837  pop     rbx
  ... truncated ...
```
