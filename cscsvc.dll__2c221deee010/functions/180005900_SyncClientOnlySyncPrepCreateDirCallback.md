# SyncClientOnlySyncPrepCreateDirCallback

- ea: `0x180005900`
- end: `0x180006098`
- name: `SyncClientOnlySyncPrepCreateDirCallback`
- size: `1944`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int, __int64, int, PHANDLE FileHandle, int, int, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180004c70`
- `0x180005900`
- `0x1800060a0`
- `0x1800223c0`
- `0x1800360c0`
- `0x180036394`
- `0x18003e928`
- `0x180044554`
- `0x180074984`
- `0x1800772e4`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005ae3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005ae3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005d84`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005d84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ad2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005d76`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ad2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005d76`

## string_xrefs

- `0x180005ec5`: `SyncClientOnlySyncPrepCreateDirCallback: Ctx: 0x%p LocalHdl: 0x%p DummyHdl: 0x%p LocalItem: 0x%p DummyItem: 0x%p `
- `0x180005b51`: `SyncClientOnlySyncPrepCreateDirCallback: NewLocal: 0x%p NewDummy: 0x%p NewContext: 0x%p EnterDir: 0x%p`
- `0x180005fe3`: `SyncClientOnlySyncPrepCreateDirCallback: Invalid local buffer! (R: %d NE: %d)`
- `0x180005f9e`: `SyncClientOnlySyncPrepCreateDirCallback: 0x%x`
- `0x180006033`: `SyncClientOnlySyncPrepCreateDirCallback: 0x%x`
- `0x180006068`: `SyncClientOnlySyncPrepCreateDirCallback: 0x%x`
- `0x180005f54`: `SyncClientOnlySyncPrepCreateDirCallback: SyncOpenUNCPathLocalForEnumeration (Local) failed with %x`
- `0x180005dcd`: `SyncClientOnlySyncPrepCreateDirCallback: Received %d on [%ws] for NEXT_ITEM`

## pseudocode

```c
__int64 __fastcall SyncClientOnlySyncPrepCreateDirCallback(
        __int64 *a1,
        void *a2,
        __int64 a3,
        _DWORD *a4,
        unsigned int a5,
        __int64 a6,
        int a7,
        PHANDLE FileHandle,
        _QWORD *a9,
        __int64 a10,
        _BYTE *a11)
{
  unsigned int DirCallback; // ebx
  CObjectMonitor *v16; // rax
  _QWORD *v17; // r12
  PHANDLE v18; // r15
  int v19; // ecx
  _BYTE *v20; // rsi
  unsigned int v21; // ebx
  unsigned int v22; // r8d
  bool v23; // cf
  unsigned int Status; // r13d
  int *v25; // rax
  __int64 v26; // rbp
  __int64 v27; // rdx
  __int64 v28; // rcx
  int *v29; // rdx
  __int64 v30; // rax
  unsigned int v32; // edi
  __int64 v33; // rbx
  HANDLE ProcessHeap; // rax
  _WORD *v35; // rax
  _WORD *v36; // rsi
  __int64 v38; // r13
  _BYTE *v39; // rsi
  __int64 v40; // rbx
  _WORD *v41; // r9
  _WORD *v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // r8
  _WORD *v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // r9
  const wchar_t *v48; // r8
  _WORD *v49; // rdx
  __int64 v50; // rcx
  _WORD *v51; // rcx
  int *v52; // rdx
  __int64 v53; // rcx
  _WORD *v54; // rax
  __int64 v55; // rax
  __int64 v56; // r11
  int *v57; // rcx
  _WORD *i; // rax
  _WORD *v59; // rcx
  __int64 v60; // rdx
  unsigned int v61; // ebx
  HANDLE v62; // rax
  int v63; // r9d
  CObjectMonitor *v64; // rax
  __int64 v65; // rbx
  int v66; // [rsp+20h] [rbp-98h]
  __int64 v67; // [rsp+38h] [rbp-80h]
  bool v68; // [rsp+50h] [rbp-68h] BYREF
  unsigned int v69; // [rsp+54h] [rbp-64h]
  __int128 v70; // [rsp+58h] [rbp-60h] BYREF
  struct _UNICODE_STRING v71; // [rsp+68h] [rbp-50h] BYREF
  __int64 v72; // [rsp+C0h] [rbp+8h] BYREF
  __int64 v73; // [rsp+D8h] [rbp+20h] BYREF

  DirCallback = 0;
  v69 = 0;
  v68 = 0;
  LOBYTE(v72) = 0;
  LOBYTE(v73) = 0;
  v70 = 0;
  v71 = 0;
  v16 = WPP_GLOBAL_Control;
  v17 = a9;
  v18 = FileHandle;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    {
      v65 = a6;
      SyncTraceOutputInternal(
        L"SyncClientOnlySyncPrepCreateDirCallback: Ctx: 0x%p LocalHdl: 0x%p DummyHdl: 0x%p LocalItem: 0x%p DummyItem: 0x%p ",
        a1,
        a2,
        a3,
        a4,
        a6);
      WPP_SF_qqqqq(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        22,
        WPP_1cdddd128e273768ef214ae69441ffcb_Traceguids,
        a1,
        a2,
        a3,
        a4,
        v65);
      v16 = WPP_GLOBAL_Control;
      DirCallback = v69;
    }
    if ( v16 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v16 + 108) & 4) != 0 )
    {
      v38 = a10;
      v39 = a11;
      SyncTraceOutputInternal(
        L"SyncClientOnlySyncPrepCreateDirCallback: NewLocal: 0x%p NewDummy: 0x%p NewContext: 0x%p EnterDir: 0x%p",
        v18,
        v17,
        a10,
        a11);
      WPP_SF_qqqq(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        23,
        WPP_1cdddd128e273768ef214ae69441ffcb_Traceguids,
        v18,
        v17,
        v38,
        v39);
    }
  }
  *v17 = 0;
  *v18 = 0;
  if ( !a4
    || (v19 = *(_DWORD *)a1[2], (v19 & 2) != 0)
    || (v19 & 0x80u) != 0
    || (*(_DWORD *)(*a1 + 8) & 0x1000) != 0 && (v19 & 0x100000) != 0 )
  {
    *a11 = 0;
    goto LABEL_69;
  }
  v20 = a11;
  v21 = a5;
  *a11 = 1;
  v22 = *a4;
  if ( *a4 )
  {
    if ( v21 < v22 )
      goto LABEL_81;
    v23 = v22 < 0xB0;
  }
  else
  {
    v23 = v21 < 0xB0;
  }
  if ( !v23 )
  {
    v71.Buffer = (PWSTR)a4 + 47;
    v71.MaximumLength = *((_WORD *)a4 + 30);
    v71.Length = v71.MaximumLength;
    Status = SyncOpenUNCPathLocalForEnumeration(
               v18,
               a2,
               &v71,
               0x81u,
               7u,
               &v68,
               (bool *)&v72,
               0,
               (*(_DWORD *)(*(_QWORD *)(*a1 + 16) + 8LL) & 0x800) != 0,
               (char *)&v73);
    if ( Status )
    {
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        SyncTraceOutputInternal(
          L"SyncClientOnlySyncPrepCreateDirCallback: SyncOpenUNCPathLocalForEnumeration (Local) failed with %x",
          Status);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 26, WPP_1cdddd128e273768ef214ae69441ffcb_Traceguids, Status);
      }
      LODWORD(a9) = 512;
      goto LABEL_13;
    }
    if ( !(_BYTE)v72 )
    {
      LODWORD(a9) = 0;
      if ( !(_BYTE)v73 )
      {
LABEL_13:
        v25 = (int *)a1[2];
        v26 = 36;
        if ( (*v25 & 0x20000000) != 0 )
        {
          v27 = 36;
        }
        else
        {
          v27 = 34;
          if ( *v25 < 0 )
            v27 = 9;
        }
        v28 = -1;
        v29 = &v25[v27];
        v30 = -1;
        do
          ++v30;
        while ( *((_WORD *)v29 + v30) );
        while ( *(_WORD *)(a1[3] + 2 * v28++ + 2) != 0 )
          ;
        ++NumAlloc;
        v32 = v30 + v28 + 3;
        v33 = 2 * v32;
        TotalAlloc += v33;
        ProcessHeap = GetProcessHeap();
        v35 = HeapAlloc(ProcessHeap, 8u, (unsigned int)v33);
        v36 = v35;
        if ( !v35 )
        {
          if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
          {
            SyncTraceOutputInternal(L"SyncClientOnlySyncPrepCreateDirCallback: 0x%x", 3221225626LL);
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              27,
              WPP_1cdddd128e273768ef214ae69441ffcb_Traceguids,
              3221225626LL);
          }
          return 3221225626LL;
        }
        v40 = 2147483646;
        if ( v32 )
        {
          if ( v32 > 0x7FFFFFFFuLL )
          {
            *v35 = 0;
          }
          else
          {
            v41 = (_WORD *)a1[3];
            v42 = v35;
            v43 = 2147483646;
            v44 = v32;
            do
            {
              if ( !v43 )
                break;
              if ( !*v41 )
                break;
              *v35++ = *v41++;
              --v43;
              --v44;
            }
            while ( v44 );
            v45 = v35 - 1;
            if ( v44 )
              v45 = v35;
            *v45 = 0;
            v46 = v32;
            do
            {
              if ( !*v42 )
                break;
              ++v42;
              --v46;
            }
            while ( v46 );
            if ( v46 )
            {
              v47 = v46;
              v48 = L"\\";
              v49 = &v36[v32 - v46];
              v50 = 2147483646;
              do
              {
                if ( !v50 )
                  break;
                if ( !*v48 )
                  break;
                *v49++ = *v48++;
                --v50;
                --v47;
              }
              while ( v47 );
              v51 = v49 - 1;
              if ( v47 )
                v51 = v49;
              *v51 = 0;
            }
          }
        }
        v52 = (int *)a1[2];
        if ( (*v52 & 0x20000000) == 0 )
        {
          v26 = 34;
          if ( *v52 < 0 )
            v26 = 9;
        }
        if ( v32 && v32 <= 0x7FFFFFFFuLL )
        {
          v53 = v32;
          v54 = v36;
          while ( *v54 )
          {
            ++v54;
            if ( !--v53 )
            {
              v55 = 0;
              goto LABEL_57;
            }
          }
          v55 = v32 - v53;
LABEL_57:
          if ( v53 )
          {
            v56 = v32 - v55;
            v57 = &v52[v26];
            for ( i = &v36[v55]; v56; --v56 )
            {
              if ( !v40 )
                break;
              if ( !*(_WORD *)v57 )
                break;
              *i = *(_WORD *)v57;
              v57 = (int *)((char *)v57 + 2);
              ++i;
              --v40;
            }
            v59 = i - 1;
            if ( v56 )
              v59 = i;
            *v59 = 0;
          }
        }
        v60 = *a1;
        *(_QWORD *)&v70 = v36;
        DWORD2(v70) = 1;
        v61 = (*(__int64 (__fastcall **)(__int128 *, _QWORD))v60)(&v70, *(_QWORD *)(v60 + 24));
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
        {
          SyncTraceOutputInternal(
            L"SyncClientOnlySyncPrepCreateDirCallback: Received %d on [%ws] for NEXT_ITEM",
            v61,
            (_QWORD)v70);
          WPP_SF_dS(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            28,
            (unsigned int)WPP_1cdddd128e273768ef214ae69441ffcb_Traceguids,
            v61,
            v70);
        }
        if ( v61 == 1 )
        {
          DirCallback = v69;
          *a11 = 0;
        }
        else if ( v61 )
        {
          *a11 = 0;
          if ( v61 == 2 )
            DirCallback = -1073741248;
          else
            DirCallback = -1073741811;
        }
        else
        {
          v63 = a10;
          v67 = (__int64)a11;
          v66 = (int)a9;
          *v17 = 0;
          DirCallback = SyncEnumDefaultCreateDirCallback(
                          (int)a1,
                          (int)v18,
                          (int)v17,
                          v63,
                          v66,
                          Status,
                          (__int64)v36,
                          v67);
        }
        ++NumFree;
        v62 = GetProcessHeap();
        HeapFree(v62, 0, v36);
        goto LABEL_69;
      }
    }
    SyncCloseFile(*v18);
    DirCallback = v69;
    *v18 = 0;
    *v20 = 0;
LABEL_69:
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
    {
      SyncTraceOutputInternal(L"SyncClientOnlySyncPrepCreateDirCallback: 0x%x", DirCallback);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 29, WPP_1cdddd128e273768ef214ae69441ffcb_Traceguids, DirCallback);
    }
    return DirCallback;
  }
LABEL_81:
  v64 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(L"SyncClientOnlySyncPrepCreateDirCallback: Invalid local buffer! (R: %d NE: %d)", v21);
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 24, WPP_1cdddd128e273768ef214ae69441ffcb_Traceguids, v21, *a4);
      v64 = WPP_GLOBAL_Control;
    }
    if ( v64 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v64 + 108) & 8) != 0 )
    {
      SyncTraceOutputInternal(L"SyncClientOnlySyncPrepCreateDirCallback: 0x%x", 3221225701LL);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 25, WPP_1cdddd128e273768ef214ae69441ffcb_Traceguids, 3221225701LL);
    }
  }
  return 3221225701LL;
}

```

## disassembly

```asm
0x180005900  mov     rax, rsp
0x180005903  mov     [rax+10h], rbx
0x180005907  push    rbp
0x180005908  push    rsi
0x180005909  push    rdi
0x18000590a  push    r12
0x18000590c  push    r13
0x18000590e  push    r14
0x180005910  push    r15
0x180005912  sub     rsp, 80h
0x180005919  xorps   xmm0, xmm0
0x18000591c  mov     rbp, rdx
0x18000591f  xor     edx, edx
0x180005921  mov     rdi, r9
0x180005924  mov     ebx, edx
0x180005926  mov     dword ptr [rsp+0B8h+var_68+4], edx
0x18000592a  mov     [rax-68h], dl
0x18000592d  mov     rsi, r8
0x180005930  mov     [rax+8], dl
0x180005933  mov     r14, rcx
0x180005936  mov     [rax+20h], dl
0x180005939  movups  xmmword ptr [rax-60h], xmm0
0x18000593d  movups  xmmword ptr [rax-50h], xmm0
0x180005941  mov     rax, cs:WPP_GLOBAL_Control
0x180005948  lea     r13, WPP_GLOBAL_Control
0x18000594f  mov     r12, [rsp+0B8h+arg_40]
0x180005957  mov     r15, [rsp+0B8h+FileHandle]
0x18000595f  cmp     rax, r13
0x180005962  jnz     loc_180005B2C
0x180005968  mov     [r12], rdx
0x18000596c  mov     [r15], rdx
0x18000596f  test    rdi, rdi
0x180005972  jz      loc_180005E75
0x180005978  mov     rax, [r14+10h]
0x18000597c  mov     ecx, [rax]
0x18000597e  test    cl, 2
0x180005981  jnz     loc_180005E75
0x180005987  test    cl, cl
0x180005989  js      loc_180005E75
0x18000598f  mov     rax, [r14]
0x180005992  test    dword ptr [rax+8], 1000h
0x180005999  jnz     loc_180005F29
0x18000599f  mov     rsi, [rsp+0B8h+arg_50]
0x1800059a7  mov     ebx, [rsp+0B8h+arg_20]
0x1800059ae  mov     byte ptr [rsi], 1
0x1800059b1  mov     r8d, [rdi]
0x1800059b4  test    r8d, r8d
0x1800059b7  jz      loc_180005E50
0x1800059bd  cmp     ebx, r8d
0x1800059c0  jb      loc_180005E5B
0x1800059c6  cmp     r8d, 0B0h
0x1800059cd  jb      loc_180005E5B
0x1800059d3  lea     rax, [rdi+5Eh]
0x1800059d7  mov     r9d, 81h
0x1800059dd  mov     [rsp+0B8h+var_48], rax
0x1800059e2  lea     r8, [rsp+0B8h+var_50]
0x1800059e7  movzx   eax, word ptr [rdi+3Ch]
0x1800059eb  mov     [rsp+0B8h+var_4E], ax
0x1800059f0  mov     [rsp+0B8h+var_50], ax
0x1800059f5  mov     rax, [r14]
0x1800059f8  mov     rcx, [rax+10h]
0x1800059fc  mov     eax, [rcx+8]
0x1800059ff  lea     rcx, [rsp+0B8h+arg_18]
0x180005a07  mov     [rsp+0B8h+var_70], rcx; __int64
0x180005a0c  mov     rcx, r15; FileHandle
0x180005a0f  shr     eax, 0Bh
0x180005a12  and     al, 1
0x180005a14  mov     [rsp+0B8h+var_78], al; char
0x180005a18  lea     rax, [rsp+0B8h+arg_0]
0x180005a20  mov     [rsp+0B8h+var_80], rdx; __int64
0x180005a25  mov     rdx, rbp
0x180005a28  mov     [rsp+0B8h+var_88], rax; __int64
0x180005a2d  lea     rax, [rsp+0B8h+var_68]
0x180005a32  mov     qword ptr [rsp+0B8h+Status], rax; __int64
0x180005a37  mov     [rsp+0B8h+var_98], 7; ULONG
0x180005a3f  call    SyncOpenUNCPathLocalForEnumeration
0x180005a44  mov     r13d, eax
0x180005a47  test    eax, eax
0x180005a49  jnz     loc_180005F38
0x180005a4f  cmp     byte ptr [rsp+0B8h+arg_0], al
0x180005a56  jnz     loc_180005E85
0x180005a5c  mov     dword ptr [rsp+0B8h+arg_40], eax
0x180005a63  cmp     byte ptr [rsp+0B8h+arg_18], al
0x180005a6a  jnz     loc_180005E85
0x180005a70  mov     rax, [r14+10h]
0x180005a74  mov     ebp, 90h
0x180005a79  mov     r8d, 24h ; '$'
0x180005a7f  mov     ecx, [rax]
0x180005a81  bt      ecx, 1Dh
0x180005a85  jnb     loc_180005BAF
0x180005a8b  mov     edx, ebp
0x180005a8d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180005a94  add     rdx, rax
0x180005a97  mov     rax, rcx
0x180005a9a  nop     word ptr [rax+rax+00h]
0x180005aa0  inc     rax
0x180005aa3  cmp     word ptr [rdx+rax*2], 0
0x180005aa8  jnz     short loc_180005AA0
0x180005aaa  mov     rdx, [r14+18h]
0x180005aae  xchg    ax, ax
0x180005ab0  cmp     word ptr [rdx+rcx*2+2], 0
0x180005ab6  lea     rcx, [rcx+1]
0x180005aba  jnz     short loc_180005AB0
0x180005abc  inc     cs:NumAlloc
0x180005ac3  lea     edi, [rcx+3]
0x180005ac6  add     edi, eax
0x180005ac8  lea     ebx, [rdi+rdi]
0x180005acb  add     cs:TotalAlloc, rbx
0x180005ad2  call    cs:__imp_GetProcessHeap
0x180005ad8  mov     r8d, ebx; dwBytes
0x180005adb  mov     edx, 8; dwFlags
0x180005ae0  mov     rcx, rax; hHeap
0x180005ae3  call    cs:__imp_HeapAlloc
0x180005ae9  mov     rsi, rax
0x180005aec  test    rax, rax
0x180005aef  jnz     loc_180005BBF
0x180005af5  mov     rax, cs:WPP_GLOBAL_Control
0x180005afc  lea     rcx, WPP_GLOBAL_Control
0x180005b03  cmp     rax, rcx
0x180005b06  jnz     loc_180005F8F
0x180005b0c  mov     eax, 0C000009Ah
0x180005b11  mov     rbx, [rsp+0B8h+arg_8]
0x180005b19  add     rsp, 80h
0x180005b20  pop     r15
0x180005b22  pop     r14
0x180005b24  pop     r13
0x180005b26  pop     r12
0x180005b28  pop     rdi
0x180005b29  pop     rsi
0x180005b2a  pop     rbp
0x180005b2b  retn
0x180005b2c  test    byte ptr [rax+6Ch], 4
0x180005b30  jnz     loc_180005EBD
0x180005b36  cmp     rax, r13
0x180005b39  jz      loc_180005968
0x180005b3f  test    byte ptr [rax+6Ch], 4
0x180005b43  jz      loc_180005968
0x180005b49  mov     r13, [rsp+0B8h+arg_48]
0x180005b51  lea     rcx, aSyncclientonly_16; "SyncClientOnlySyncPrepCreateDirCallback"...
0x180005b58  mov     rsi, [rsp+0B8h+arg_50]
0x180005b60  mov     r9, r13
0x180005b63  mov     r8, r12
0x180005b66  mov     qword ptr [rsp+0B8h+var_98], rsi
0x180005b6b  mov     rdx, r15
0x180005b6e  call    SyncTraceOutputInternal
0x180005b73  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b7a  lea     r8, WPP_1cdddd128e273768ef214ae69441ffcb_Traceguids
0x180005b81  mov     [rsp+0B8h+var_88], rsi
0x180005b86  mov     edx, 17h
0x180005b8b  mov     qword ptr [rsp+0B8h+Status], r13
0x180005b90  mov     r9, r15
0x180005b93  mov     qword ptr [rsp+0B8h+var_98], r12
0x180005b98  mov     rcx, [rcx+60h]
0x180005b9c  call    WPP_SF_qqqq
0x180005ba1  xor     edx, edx
0x180005ba3  lea     r13, WPP_GLOBAL_Control
0x180005baa  jmp     loc_180005968
0x180005baf  test    ecx, ecx
0x180005bb1  mov     edx, 88h
0x180005bb6  cmovs   rdx, r8
0x180005bba  jmp     loc_180005A8D
0x180005bbf  mov     r11d, edi
0x180005bc2  mov     ebx, 7FFFFFFEh
0x180005bc7  test    edi, edi
0x180005bc9  jz      loc_180005C97
0x180005bcf  cmp     r11, 7FFFFFFFh
0x180005bd6  ja      short loc_180005C1A
0x180005bd8  mov     r9, [r14+18h]
0x180005bdc  mov     rdx, rsi
0x180005bdf  mov     ecx, ebx
0x180005be1  mov     r8d, r11d
0x180005be4  test    rcx, rcx
0x180005be7  jz      short loc_180005C08
0x180005be9  movzx   r10d, word ptr [r9]
0x180005bed  test    r10w, r10w
0x180005bf1  jz      short loc_180005C08
0x180005bf3  mov     [rax], r10w
0x180005bf7  add     r9, 2
0x180005bfb  add     rax, 2
0x180005bff  dec     rcx
0x180005c02  sub     r8, 1
0x180005c06  jnz     short loc_180005BE4
0x180005c08  test    r8, r8
0x180005c0b  lea     rcx, [rax-2]
0x180005c0f  cmovnz  rcx, rax
0x180005c13  xor     eax, eax
0x180005c15  mov     [rcx], ax
0x180005c18  jmp     short loc_180005C2B
0x180005c1a  xor     eax, eax
0x180005c1c  mov     [rsi], ax
0x180005c1f  cmp     r11, 7FFFFFFFh
0x180005c26  ja      short loc_180005C97
0x180005c28  mov     rdx, rsi
0x180005c2b  mov     rcx, r11
0x180005c2e  mov     r9, r11
0x180005c31  cmp     word ptr [rdx], 0
0x180005c35  jz      short loc_180005C41
0x180005c37  add     rdx, 2
0x180005c3b  sub     rcx, 1
0x180005c3f  jnz     short loc_180005C31
0x180005c41  xor     eax, eax
0x180005c43  mov     rdx, r9
0x180005c46  sub     rdx, rcx
0x180005c49  test    rcx, rcx
0x180005c4c  cmovz   rdx, rax
0x180005c50  jz      short loc_180005C97
0x180005c52  sub     r9, rdx
0x180005c55  lea     r8, Src; "\\"
0x180005c5c  lea     rdx, [rsi+rdx*2]
0x180005c60  mov     rcx, rbx
0x180005c63  jz      short loc_180005C87
0x180005c65  test    rcx, rcx
0x180005c68  jz      short loc_180005C87
0x180005c6a  movzx   eax, word ptr [r8]
0x180005c6e  test    ax, ax
0x180005c71  jz      short loc_180005C87
0x180005c73  mov     [rdx], ax
0x180005c76  add     r8, 2
0x180005c7a  add     rdx, 2
0x180005c7e  dec     rcx
0x180005c81  sub     r9, 1
0x180005c85  jnz     short loc_180005C65
0x180005c87  test    r9, r9
0x180005c8a  lea     rcx, [rdx-2]
0x180005c8e  cmovnz  rcx, rdx
0x180005c92  xor     eax, eax
0x180005c94  mov     [rcx], ax
0x180005c97  mov     rdx, [r14+10h]
0x180005c9b  mov     eax, [rdx]
0x180005c9d  bt      eax, 1Dh
0x180005ca1  jnb     loc_180005DAE
0x180005ca7  test    edi, edi
0x180005ca9  jz      short loc_180005D21
0x180005cab  cmp     r11, 7FFFFFFFh
0x180005cb2  ja      short loc_180005D21
0x180005cb4  mov     rcx, r11
0x180005cb7  mov     rax, rsi
0x180005cba  nop     word ptr [rax+rax+00h]
0x180005cc0  cmp     word ptr [rax], 0
0x180005cc4  jz      short loc_180005CD4
0x180005cc6  add     rax, 2
0x180005cca  sub     rcx, 1
0x180005cce  jnz     short loc_180005CC0
0x180005cd0  xor     eax, eax
0x180005cd2  jmp     short loc_180005CDA
0x180005cd4  mov     rax, r11
0x180005cd7  sub     rax, rcx
0x180005cda  test    rcx, rcx
0x180005cdd  jz      short loc_180005D21
0x180005cdf  sub     r11, rax
0x180005ce2  lea     rcx, [rdx+rbp]
0x180005ce6  lea     rax, [rsi+rax*2]
0x180005cea  jz      short loc_180005D11
0x180005cec  nop     dword ptr [rax+00h]
0x180005cf0  test    rbx, rbx
0x180005cf3  jz      short loc_180005D11
0x180005cf5  movzx   edx, word ptr [rcx]
0x180005cf8  test    dx, dx
0x180005cfb  jz      short loc_180005D11
0x180005cfd  mov     [rax], dx
0x180005d00  add     rcx, 2
0x180005d04  add     rax, 2
0x180005d08  dec     rbx
0x180005d0b  sub     r11, 1
0x180005d0f  jnz     short loc_180005CF0
0x180005d11  test    r11, r11
0x180005d14  lea     rcx, [rax-2]
0x180005d18  cmovnz  rcx, rax
0x180005d1c  xor     eax, eax
0x180005d1e  mov     [rcx], ax
0x180005d21  mov     rdx, [r14]
0x180005d24  lea     rcx, [rsp+0B8h+var_60]
0x180005d29  mov     [rsp+0B8h+var_60], rsi
0x180005d2e  mov     [rsp+0B8h+var_58], 1
0x180005d36  mov     rax, [rdx]
0x180005d39  mov     rdx, [rdx+18h]
0x180005d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d42  mov     ebx, eax
0x180005d44  mov     rax, cs:WPP_GLOBAL_Control
0x180005d4b  lea     rcx, WPP_GLOBAL_Control
0x180005d52  cmp     rax, rcx
0x180005d55  jnz     short loc_180005DC2
0x180005d57  mov     rax, [rsp+0B8h+arg_50]
0x180005d5f  cmp     ebx, 1
0x180005d62  jnz     loc_180005E09
0x180005d68  mov     ebx, dword ptr [rsp+0B8h+var_68+4]
0x180005d6c  mov     byte ptr [rax], 0
0x180005d6f  inc     cs:NumFree
0x180005d76  call    cs:__imp_GetProcessHeap
0x180005d7c  mov     r8, rsi; lpMem
0x180005d7f  xor     edx, edx; dwFlags
0x180005d81  mov     rcx, rax; hHeap
0x180005d84  call    cs:__imp_HeapFree
0x180005d8a  lea     r13, WPP_GLOBAL_Control
0x180005d91  mov     rax, cs:WPP_GLOBAL_Control
0x180005d98  cmp     rax, r13
0x180005d9b  jz      short loc_180005DA7
0x180005d9d  test    byte ptr [rax+6Ch], 8
0x180005da1  jnz     loc_180006066
0x180005da7  mov     eax, ebx
  ... truncated ...
```
