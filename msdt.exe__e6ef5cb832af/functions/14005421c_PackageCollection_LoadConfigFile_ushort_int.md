# PackageCollection::LoadConfigFile(ushort *,int)

- ea: `0x14005421c`
- end: `0x1400548d3`
- name: `?LoadConfigFile@PackageCollection@@AEAAJPEAGH@Z`
- size: `1719`
- prototype: `__int64 __fastcall(PackageCollection *__hidden this, OLECHAR *psz, int)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x1400531d0`

## callees

- `0x140001d54`
- `0x14000706c`
- `0x140020420`
- `0x140053e10`
- `0x1400540d8`
- `0x14005421c`
- `0x1400548dc`
- `0x1400565f4`
- `0x140056dcc`
- `0x1400573b8`
- `0x1400574d4`
- `0x140059e6c`
- `0x140059f08`
- `0x14005aea4`
- `0x14005b520`
- `0x14005b944`
- `0x140063010`

## import_xrefs

- `KERNEL32!SetCurrentDirectoryW` at `0x1400547dc`
- `KERNEL32!SetCurrentDirectoryW` at `0x1400547dc`
- `KERNEL32!GetCurrentDirectoryW` at `0x140054325`
- `KERNEL32!GetCurrentDirectoryW` at `0x140054325`
- `KERNEL32!GetLastError` at `0x140054335`
- `KERNEL32!GetLastError` at `0x140054335`
- `KERNEL32!HeapAlloc` at `0x1400542d8`
- `KERNEL32!HeapAlloc` at `0x14005437f`
- `KERNEL32!HeapAlloc` at `0x1400542d8`
- `KERNEL32!HeapAlloc` at `0x14005437f`
- `KERNEL32!HeapFree` at `0x1400544cf`
- `KERNEL32!HeapFree` at `0x14005470b`
- `KERNEL32!HeapFree` at `0x140054862`
- `KERNEL32!HeapFree` at `0x14005488b`
- `KERNEL32!HeapFree` at `0x1400548b0`
- `KERNEL32!HeapFree` at `0x1400544cf`
- `KERNEL32!HeapFree` at `0x14005470b`
- `KERNEL32!HeapFree` at `0x140054862`
- `KERNEL32!HeapFree` at `0x14005488b`
- `KERNEL32!HeapFree` at `0x1400548b0`
- `KERNEL32!GetProcessHeap` at `0x1400542c1`
- `KERNEL32!GetProcessHeap` at `0x140054368`
- `KERNEL32!GetProcessHeap` at `0x1400544bb`
- `KERNEL32!GetProcessHeap` at `0x1400546f7`
- `KERNEL32!GetProcessHeap` at `0x14005484e`
- `KERNEL32!GetProcessHeap` at `0x140054877`
- `KERNEL32!GetProcessHeap` at `0x14005489c`
- `KERNEL32!GetProcessHeap` at `0x1400542c1`
- `KERNEL32!GetProcessHeap` at `0x140054368`
- `KERNEL32!GetProcessHeap` at `0x1400544bb`
- `KERNEL32!GetProcessHeap` at `0x1400546f7`
- `KERNEL32!GetProcessHeap` at `0x14005484e`
- `KERNEL32!GetProcessHeap` at `0x140054877`
- `KERNEL32!GetProcessHeap` at `0x14005489c`
- `OLEAUT32!__imp_SysFreeString` at `0x14005449f`
- `OLEAUT32!__imp_SysFreeString` at `0x1400546df`
- `OLEAUT32!__imp_SysFreeString` at `0x14005483d`
- `OLEAUT32!__imp_SysFreeString` at `0x14005449f`
- `OLEAUT32!__imp_SysFreeString` at `0x1400546df`
- `OLEAUT32!__imp_SysFreeString` at `0x14005483d`

## string_xrefs

- `0x140054303`: `PackageCollection::LoadConfigFile`
- `0x14005462c`: `PackageCollection::LoadConfigFile`
- `0x140054659`: `PackageCollection::LoadConfigFile`
- `0x14005468d`: `PackageCollection::LoadConfigFile`
- `0x140054736`: `PackageCollection::LoadConfigFile`
- `0x14005476e`: `PackageCollection::LoadConfigFile`
- `0x1400543f7`: `cfg:PackageConfiguration/cfg:Execution/cfg:Package[@Path]`

## pseudocode

```c
__int64 __fastcall PackageCollection::LoadConfigFile(PackageCollection *this, OLECHAR *psz, int a3)
{
  WCHAR *v5; // r12
  OLECHAR *v6; // r14
  int v7; // r15d
  int DisplayNodesFromFile; // eax
  const unsigned __int16 *v10; // rdx
  signed int v11; // ebx
  int v12; // r9d
  HANDLE ProcessHeap; // rax
  WCHAR *v14; // rax
  signed int LastError; // eax
  HANDLE v16; // rax
  void *v17; // rax
  const WCHAR *v18; // r15
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  __int64 v23; // r15
  unsigned int v24; // esi
  HANDLE v25; // rax
  Package *v26; // rax
  Package *v27; // rcx
  int Answers; // eax
  const unsigned __int16 *v29; // rdx
  int Attribute; // eax
  int v31; // eax
  int v32; // r9d
  HANDLE v33; // rax
  __int64 v34; // rsi
  __int64 v35; // rcx
  WCHAR *v36; // rsi
  HANDLE v37; // rax
  void *v38; // rdi
  HANDLE v39; // rax
  HANDLE v40; // rax
  int v42; // [rsp+20h] [rbp-49h]
  struct IXMLDOMNode *v43; // [rsp+30h] [rbp-39h] BYREF
  int v44; // [rsp+38h] [rbp-31h]
  LPVOID lpMem; // [rsp+40h] [rbp-29h]
  int v46; // [rsp+48h] [rbp-21h] BYREF
  LPCWSTR v47; // [rsp+50h] [rbp-19h]
  LPCWSTR lpPathName; // [rsp+58h] [rbp-11h]
  struct IXMLDOMDocument2 *v49; // [rsp+60h] [rbp-9h] BYREF
  __int64 v50; // [rsp+68h] [rbp-1h] BYREF
  LPCWSTR v51; // [rsp+70h] [rbp+7h] BYREF
  LPCWSTR lpSrc; // [rsp+78h] [rbp+Fh] BYREF
  unsigned int v53; // [rsp+E8h] [rbp+7Fh]

  lpMem = 0;
  v5 = 0;
  v51 = 0;
  v6 = 0;
  lpPathName = 0;
  v7 = 0;
  v47 = 0;
  lpSrc = 0;
  v49 = 0;
  v43 = 0;
  v50 = 0;
  v46 = 0;
  v53 = 0;
  v44 = 0;
  DisplayNodesFromFile = MetXmlLoad(psz, &v49);
  v11 = DisplayNodesFromFile;
  if ( DisplayNodesFromFile < 0 )
  {
    v12 = 1564;
LABEL_10:
    v42 = DisplayNodesFromFile;
LABEL_11:
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::LoadConfigFile", v12, v42);
    goto LABEL_73;
  }
  DisplayNodesFromFile = MetXmlSetSelectionNamespace(v49, v10);
  v11 = DisplayNodesFromFile;
  if ( DisplayNodesFromFile < 0 )
  {
    v12 = 1567;
    goto LABEL_10;
  }
  if ( a3 )
  {
    DisplayNodesFromFile = PackageCollection::LoadDisplayNodesFromFile(this, v49);
    v11 = DisplayNodesFromFile;
    if ( DisplayNodesFromFile < 0 )
    {
      v12 = 1574;
      goto LABEL_10;
    }
  }
  ProcessHeap = GetProcessHeap();
  v14 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x208u);
  lpPathName = v14;
  if ( !v14 )
  {
    DisplayNodesFromFile = -2147024882;
    v12 = 1581;
    v11 = -2147024882;
    goto LABEL_10;
  }
  if ( !GetCurrentDirectoryW(0x104u, v14) )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( v11 < 0 )
    {
      v42 = v11;
      v12 = 1584;
      goto LABEL_11;
    }
  }
  v44 = 1;
  v16 = GetProcessHeap();
  v17 = HeapAlloc(v16, 0, 0x208u);
  lpMem = v17;
  v18 = (const WCHAR *)v17;
  if ( !v17 )
  {
    v11 = -2147024882;
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::LoadConfigFile", 1588, -2147024882);
LABEL_72:
    v7 = 0;
    goto LABEL_73;
  }
  v19 = StringCchCopyW((unsigned __int16 *)v17, 0x104u, psz);
  v11 = v19;
  if ( v19 < 0 )
  {
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::LoadConfigFile", 1591, v19);
    goto LABEL_72;
  }
  v20 = MetSetCurrentDirectoryByFile(v18);
  v11 = v20;
  if ( v20 < 0 )
  {
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::LoadConfigFile", 1594, v20);
    goto LABEL_72;
  }
  v21 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, const wchar_t *, __int64 *))v49->lpVtbl->selectNodes)(
          v49,
          L"cfg:PackageConfiguration/cfg:Execution/cfg:Package[@Path]",
          &v50);
  v11 = v21;
  if ( v21 < 0 )
  {
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::LoadConfigFile", 1600, v21);
    goto LABEL_72;
  }
  v22 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v50 + 64LL))(v50, &v46);
  v11 = v22;
  if ( v22 < 0 )
  {
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::LoadConfigFile", 1603, v22);
    goto LABEL_72;
  }
  if ( !v46 || v46 > 16 )
  {
    v11 = -2147024809;
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::LoadConfigFile", 1607, -2147024809);
    goto LABEL_72;
  }
  if ( v46 < 0 )
  {
    v11 = -2147024362;
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::LoadConfigFile", 1611, -2147024362);
    v7 = -1;
    v53 = -1;
  }
  else
  {
    v23 = 0;
    v53 = v46;
    v11 = 0;
    v24 = v46;
    while ( (unsigned int)v23 < v24 )
    {
      if ( v43 )
      {
        ((void (*)(void))v43->lpVtbl->Release)();
        v43 = 0;
      }
      if ( v6 )
      {
        SysFreeString(v6);
        v6 = 0;
        v47 = 0;
        lpSrc = 0;
      }
      if ( v5 )
      {
        v25 = GetProcessHeap();
        HeapFree(v25, 0, v5);
        v5 = 0;
        v51 = 0;
      }
      v26 = (Package *)operator new(0xA0u);
      if ( v26 )
        v27 = Package::Package(v26);
      else
        v27 = 0;
      *(_QWORD *)(*((_QWORD *)this + 5) + 8 * v23) = v27;
      if ( !*(_QWORD *)(*((_QWORD *)this + 5) + 8 * v23) )
      {
        Answers = -2147024882;
        v32 = 1619;
        v11 = -2147024882;
        goto LABEL_60;
      }
      Answers = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMNode **))(*(_QWORD *)v50 + 72LL))(v50, &v43);
      v11 = Answers;
      if ( Answers < 0 )
      {
        v32 = 1622;
LABEL_60:
        SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::LoadConfigFile", v32, Answers);
        goto LABEL_61;
      }
      Attribute = MetXmlGetAttribute(v43, v29, (unsigned __int16 **)&lpSrc);
      v11 = Attribute;
      if ( Attribute < 0 )
      {
        SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::LoadConfigFile", 1625, Attribute);
        v6 = (OLECHAR *)lpSrc;
        v47 = lpSrc;
        goto LABEL_61;
      }
      v6 = (OLECHAR *)lpSrc;
      v47 = lpSrc;
      Answers = MetExpandVariables((unsigned __int16 *)lpMem, 0x104u, lpSrc);
      v11 = Answers;
      if ( Answers < 0 )
      {
        v32 = 1631;
        goto LABEL_60;
      }
      v31 = MetCanonicalizeFilePath((LPCWSTR)lpMem, (unsigned __int16 **)&v51);
      v11 = v31;
      if ( v31 < 0 )
      {
        SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::LoadConfigFile", 1634, v31);
        v5 = (WCHAR *)v51;
LABEL_61:
        v7 = v53;
        goto LABEL_73;
      }
      v5 = (WCHAR *)v51;
      Answers = Package::set_PackageLocation(*(Package **)(*((_QWORD *)this + 5) + 8 * v23), v51);
      v11 = Answers;
      if ( Answers < 0 )
      {
        v32 = 1637;
        goto LABEL_60;
      }
      Answers = PackageCollection::LoadAnswers(
                  this,
                  v43,
                  *(struct Package **)(*((_QWORD *)this + 5) + 8 * v23),
                  v23 == 0);
      v11 = Answers;
      if ( Answers < 0 )
      {
        v32 = 1643;
        goto LABEL_60;
      }
      Answers = Package::set_Prereqs(*(Package **)(*((_QWORD *)this + 5) + 8 * v23), v43);
      v11 = Answers;
      if ( Answers < 0 )
      {
        v32 = 1649;
        goto LABEL_60;
      }
      Answers = PackageCollection::InitializePackage(this, v5, *(struct Package **)(*((_QWORD *)this + 5) + 8 * v23));
      v11 = Answers;
      if ( Answers < 0 )
      {
        v32 = 1655;
        goto LABEL_60;
      }
      v24 = v53;
      v23 = (unsigned int)(v23 + 1);
    }
    if ( v43 )
    {
      ((void (*)(void))v43->lpVtbl->Release)();
      v43 = 0;
    }
    if ( v6 )
    {
      SysFreeString(v6);
      v6 = 0;
      v47 = 0;
    }
    if ( v5 )
    {
      v33 = GetProcessHeap();
      HeapFree(v33, 0, v5);
      v5 = 0;
    }
    *((_DWORD *)this + 9) = v24;
    if ( v11 >= 0 )
      goto LABEL_80;
    v44 = 1;
    v7 = v24;
    v53 = v24;
  }
LABEL_73:
  if ( *((_QWORD *)this + 5) )
  {
    v34 = 0;
    if ( v7 )
    {
      do
      {
        v35 = *(_QWORD *)(*((_QWORD *)this + 5) + 8 * v34);
        if ( v35 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
          *(_QWORD *)(*((_QWORD *)this + 5) + 8 * v34) = 0;
        }
        v34 = (unsigned int)(v34 + 1);
      }
      while ( (unsigned int)v34 < v53 );
      v6 = (OLECHAR *)v47;
    }
  }
  *((_DWORD *)this + 9) = 0;
  if ( v44 )
  {
LABEL_80:
    v36 = (WCHAR *)lpPathName;
    SetCurrentDirectoryW(lpPathName);
    goto LABEL_82;
  }
  v36 = (WCHAR *)lpPathName;
LABEL_82:
  if ( v49 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v49->lpVtbl->Release)(v49);
  if ( v43 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v43->lpVtbl->Release)(v43);
    v43 = 0;
  }
  if ( v50 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    v50 = 0;
  }
  if ( v6 )
    SysFreeString(v6);
  if ( v5 )
  {
    v37 = GetProcessHeap();
    HeapFree(v37, 0, v5);
  }
  v38 = lpMem;
  if ( lpMem )
  {
    v39 = GetProcessHeap();
    HeapFree(v39, 0, v38);
  }
  if ( v36 )
  {
    v40 = GetProcessHeap();
    HeapFree(v40, 0, v36);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14005421c  push    rbp
0x14005421e  push    rbx
0x14005421f  push    rsi
0x140054220  push    rdi
0x140054221  push    r12
0x140054223  push    r13
0x140054225  push    r14
0x140054227  push    r15
0x140054229  lea     rbp, [rsp-1Fh]
0x14005422e  sub     rsp, 88h
0x140054235  mov     r13, rcx
0x140054238  mov     rsi, rdx
0x14005423b  xor     ecx, ecx
0x14005423d  lea     rdx, [rbp+57h+var_60]; struct IXMLDOMDocument2 **
0x140054241  mov     [rbp+57h+lpMem], rcx
0x140054245  mov     r12d, ecx
0x140054248  mov     [rbp+57h+var_50], rcx
0x14005424c  mov     r14d, ecx
0x14005424f  mov     [rbp+57h+lpPathName], rcx
0x140054253  mov     r15d, ecx
0x140054256  mov     [rbp+57h+var_70], rcx
0x14005425a  mov     edi, r8d
0x14005425d  mov     [rbp+57h+lpSrc], rcx
0x140054261  mov     [rbp+57h+var_60], rcx
0x140054265  mov     [rbp+57h+var_90], rcx
0x140054269  mov     [rbp+57h+var_58], rcx
0x14005426d  mov     [rbp+57h+var_78], ecx
0x140054270  mov     [rbp+57h+arg_18], ecx
0x140054273  mov     [rbp+57h+var_88], ecx
0x140054276  mov     rcx, rsi; psz
0x140054279  call    ?MetXmlLoad@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; MetXmlLoad(ushort const *,IXMLDOMDocument2 * *)
0x14005427e  mov     ebx, eax
0x140054280  test    eax, eax
0x140054282  jns     short loc_14005428C
0x140054284  mov     r9d, 61Ch
0x14005428a  jmp     short loc_1400542FA
0x14005428c  mov     rcx, [rbp+57h+var_60]; struct IXMLDOMDocument2 *
0x140054290  call    ?MetXmlSetSelectionNamespace@@YAJPEAUIXMLDOMDocument2@@PEBG@Z; MetXmlSetSelectionNamespace(IXMLDOMDocument2 *,ushort const *)
0x140054295  mov     ebx, eax
0x140054297  test    eax, eax
0x140054299  jns     short loc_1400542A3
0x14005429b  mov     r9d, 61Fh
0x1400542a1  jmp     short loc_1400542FA
0x1400542a3  test    edi, edi
0x1400542a5  jz      short loc_1400542C1
0x1400542a7  mov     rdx, [rbp+57h+var_60]; struct IXMLDOMDocument2 *
0x1400542ab  mov     rcx, r13; this
0x1400542ae  call    ?LoadDisplayNodesFromFile@PackageCollection@@AEAAJPEAUIXMLDOMDocument2@@@Z; PackageCollection::LoadDisplayNodesFromFile(IXMLDOMDocument2 *)
0x1400542b3  mov     ebx, eax
0x1400542b5  test    eax, eax
0x1400542b7  jns     short loc_1400542C1
0x1400542b9  mov     r9d, 626h
0x1400542bf  jmp     short loc_1400542FA
0x1400542c1  call    cs:__imp_GetProcessHeap
0x1400542c8  nop     dword ptr [rax+rax+00h]
0x1400542cd  xor     edx, edx; dwFlags
0x1400542cf  mov     r8d, 208h; dwBytes
0x1400542d5  mov     rcx, rax; hHeap
0x1400542d8  call    cs:__imp_HeapAlloc
0x1400542df  nop     dword ptr [rax+rax+00h]
0x1400542e4  mov     [rbp+57h+lpPathName], rax
0x1400542e8  test    rax, rax
0x1400542eb  jnz     short loc_14005431D
0x1400542ed  mov     eax, 8007000Eh
0x1400542f2  mov     r9d, 62Dh
0x1400542f8  mov     ebx, eax
0x1400542fa  mov     [rsp+0C0h+var_A0], eax
0x1400542fe  mov     edi, 1
0x140054303  lea     r8, aPackagecollect_21; "PackageCollection::LoadConfigFile"
0x14005430a  mov     ecx, edi; Level
0x14005430c  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x140054313  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140054318  jmp     loc_140054786
0x14005431d  mov     rdx, rax; lpBuffer
0x140054320  mov     ecx, 104h; nBufferLength
0x140054325  call    cs:__imp_GetCurrentDirectoryW
0x14005432c  nop     dword ptr [rax+rax+00h]
0x140054331  test    eax, eax
0x140054333  jnz     short loc_140054360
0x140054335  call    cs:__imp_GetLastError
0x14005433c  nop     dword ptr [rax+rax+00h]
0x140054341  mov     ebx, eax
0x140054343  test    eax, eax
0x140054345  jle     short loc_140054350
0x140054347  movzx   ebx, ax
0x14005434a  or      ebx, 80070000h
0x140054350  test    ebx, ebx
0x140054352  jns     short loc_140054360
0x140054354  mov     [rsp+0C0h+var_A0], ebx
0x140054358  mov     r9d, 630h
0x14005435e  jmp     short loc_1400542FE
0x140054360  mov     edi, 1
0x140054365  mov     [rbp+57h+var_88], edi
0x140054368  call    cs:__imp_GetProcessHeap
0x14005436f  nop     dword ptr [rax+rax+00h]
0x140054374  xor     edx, edx; dwFlags
0x140054376  mov     r8d, 208h; dwBytes
0x14005437c  mov     rcx, rax; hHeap
0x14005437f  call    cs:__imp_HeapAlloc
0x140054386  nop     dword ptr [rax+rax+00h]
0x14005438b  mov     [rbp+57h+lpMem], rax
0x14005438f  mov     r15, rax
0x140054392  test    rax, rax
0x140054395  jnz     short loc_1400543AD
0x140054397  mov     eax, 8007000Eh
0x14005439c  mov     r9d, 634h
0x1400543a2  mov     ebx, eax
0x1400543a4  mov     [rsp+0C0h+var_A0], eax
0x1400543a8  jmp     loc_14005476E
0x1400543ad  mov     r8, rsi; unsigned __int16 *
0x1400543b0  mov     edx, 104h; unsigned __int64
0x1400543b5  mov     rcx, r15; unsigned __int16 *
0x1400543b8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400543bd  mov     ebx, eax
0x1400543bf  test    eax, eax
0x1400543c1  jns     short loc_1400543D2
0x1400543c3  mov     [rsp+0C0h+var_A0], eax
0x1400543c7  mov     r9d, 637h
0x1400543cd  jmp     loc_14005476E
0x1400543d2  mov     rcx, r15; lpPathName
0x1400543d5  call    ?MetSetCurrentDirectoryByFile@@YAJPEAG@Z; MetSetCurrentDirectoryByFile(ushort *)
0x1400543da  mov     ebx, eax
0x1400543dc  test    eax, eax
0x1400543de  jns     short loc_1400543EF
0x1400543e0  mov     [rsp+0C0h+var_A0], eax
0x1400543e4  mov     r9d, 63Ah
0x1400543ea  jmp     loc_14005476E
0x1400543ef  mov     rcx, [rbp+57h+var_60]
0x1400543f3  lea     r8, [rbp+57h+var_58]
0x1400543f7  lea     rdx, aCfgPackageconf_1; "cfg:PackageConfiguration/cfg:Execution/"...
0x1400543fe  mov     rax, [rcx]
0x140054401  mov     rax, [rax+120h]
0x140054408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005440d  mov     ebx, eax
0x14005440f  test    eax, eax
0x140054411  jns     short loc_140054422
0x140054413  mov     [rsp+0C0h+var_A0], eax
0x140054417  mov     r9d, 640h
0x14005441d  jmp     loc_14005476E
0x140054422  mov     rcx, [rbp+57h+var_58]
0x140054426  lea     rdx, [rbp+57h+var_78]
0x14005442a  mov     rax, [rcx]
0x14005442d  mov     rax, [rax+40h]
0x140054431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140054436  mov     ebx, eax
0x140054438  test    eax, eax
0x14005443a  jns     short loc_14005444B
0x14005443c  mov     [rsp+0C0h+var_A0], eax
0x140054440  mov     r9d, 643h
0x140054446  jmp     loc_14005476E
0x14005444b  mov     eax, [rbp+57h+var_78]
0x14005444e  test    eax, eax
0x140054450  jz      loc_14005475F
0x140054456  cmp     eax, 10h
0x140054459  jg      loc_14005475F
0x14005445f  test    eax, eax
0x140054461  js      loc_140054731
0x140054467  xor     r15d, r15d
0x14005446a  mov     [rbp+57h+arg_18], eax
0x14005446d  xor     ebx, ebx
0x14005446f  mov     esi, eax
0x140054471  mov     rcx, [rbp+57h+var_90]
0x140054475  cmp     r15d, esi
0x140054478  jnb     loc_1400546AF
0x14005447e  test    rcx, rcx
0x140054481  jz      short loc_140054497
0x140054483  mov     rax, [rcx]
0x140054486  mov     rax, [rax+10h]
0x14005448a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005448f  mov     [rbp+57h+var_90], 0
0x140054497  test    r14, r14
0x14005449a  jz      short loc_1400544B6
0x14005449c  mov     rcx, r14; bstrString
0x14005449f  call    cs:__imp_SysFreeString
0x1400544a6  nop     dword ptr [rax+rax+00h]
0x1400544ab  xor     r14d, r14d
0x1400544ae  mov     [rbp+57h+var_70], r14
0x1400544b2  mov     [rbp+57h+lpSrc], r14
0x1400544b6  test    r12, r12
0x1400544b9  jz      short loc_1400544E2
0x1400544bb  call    cs:__imp_GetProcessHeap
0x1400544c2  nop     dword ptr [rax+rax+00h]
0x1400544c7  mov     r8, r12; lpMem
0x1400544ca  xor     edx, edx; dwFlags
0x1400544cc  mov     rcx, rax; hHeap
0x1400544cf  call    cs:__imp_HeapFree
0x1400544d6  nop     dword ptr [rax+rax+00h]
0x1400544db  xor     r12d, r12d
0x1400544de  mov     [rbp+57h+var_50], r12
0x1400544e2  mov     ecx, 0A0h; Size
0x1400544e7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400544ec  test    rax, rax
0x1400544ef  jz      short loc_1400544FE
0x1400544f1  mov     rcx, rax; this
0x1400544f4  call    ??0Package@@QEAA@XZ; Package::Package(void)
0x1400544f9  mov     rcx, rax
0x1400544fc  jmp     short loc_140054500
0x1400544fe  xor     ecx, ecx
0x140054500  mov     rax, [r13+28h]
0x140054504  mov     [rax+r15*8], rcx
0x140054508  mov     rax, [r13+28h]
0x14005450c  cmp     qword ptr [rax+r15*8], 0
0x140054511  jz      loc_140054680
0x140054517  mov     rcx, [rbp+57h+var_58]
0x14005451b  lea     rdx, [rbp+57h+var_90]
0x14005451f  mov     rax, [rcx]
0x140054522  mov     rax, [rax+48h]
0x140054526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005452b  mov     ebx, eax
0x14005452d  test    eax, eax
0x14005452f  js      loc_140054678
0x140054535  mov     rcx, [rbp+57h+var_90]; struct IXMLDOMNode *
0x140054539  lea     r8, [rbp+57h+lpSrc]; unsigned __int16 **
0x14005453d  call    ?MetXmlGetAttribute@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAG@Z; MetXmlGetAttribute(IXMLDOMNode *,ushort const *,ushort * *)
0x140054542  mov     ebx, eax
0x140054544  test    eax, eax
0x140054546  js      loc_14005464F
0x14005454c  mov     r14, [rbp+57h+lpSrc]
0x140054550  mov     edx, 104h; unsigned __int64
0x140054555  mov     rcx, [rbp+57h+lpMem]; unsigned __int16 *
0x140054559  mov     r8, r14; lpSrc
0x14005455c  mov     [rbp+57h+var_70], r14
0x140054560  call    ?MetExpandVariables@@YAJPEAG_KPEBG@Z; MetExpandVariables(ushort *,unsigned __int64,ushort const *)
0x140054565  mov     ebx, eax
0x140054567  test    eax, eax
0x140054569  js      loc_140054647
0x14005456f  mov     rcx, [rbp+57h+lpMem]; lpFileName
0x140054573  lea     rdx, [rbp+57h+var_50]; unsigned __int16 **
0x140054577  call    ?MetCanonicalizeFilePath@@YAJPEBGPEAPEAG@Z; MetCanonicalizeFilePath(ushort const *,ushort * *)
0x14005457c  mov     ebx, eax
0x14005457e  test    eax, eax
0x140054580  js      loc_140054622
0x140054586  mov     rcx, [r13+28h]
0x14005458a  mov     r12, [rbp+57h+var_50]
0x14005458e  mov     rdx, r12; unsigned __int16 *
0x140054591  mov     rcx, [rcx+r15*8]; this
0x140054595  call    ?set_PackageLocation@Package@@QEAAJPEBG@Z; Package::set_PackageLocation(ushort const *)
0x14005459a  mov     ebx, eax
0x14005459c  test    eax, eax
0x14005459e  js      short loc_14005461A
0x1400545a0  mov     r8, [r13+28h]
0x1400545a4  xor     r9d, r9d
0x1400545a7  mov     rdx, [rbp+57h+var_90]; struct IXMLDOMNode *
0x1400545ab  test    r15d, r15d
0x1400545ae  mov     rcx, r13; this
0x1400545b1  setz    r9b; int
0x1400545b5  mov     r8, [r8+r15*8]; struct Package *
0x1400545b9  call    ?LoadAnswers@PackageCollection@@AEAAJPEAUIXMLDOMNode@@PEAVPackage@@H@Z; PackageCollection::LoadAnswers(IXMLDOMNode *,Package *,int)
0x1400545be  mov     ebx, eax
0x1400545c0  test    eax, eax
0x1400545c2  js      short loc_140054612
0x1400545c4  mov     rcx, [r13+28h]
0x1400545c8  mov     rdx, [rbp+57h+var_90]; struct IXMLDOMNode *
0x1400545cc  mov     rcx, [rcx+r15*8]; this
0x1400545d0  call    ?set_Prereqs@Package@@QEAAJPEAUIXMLDOMNode@@@Z; Package::set_Prereqs(IXMLDOMNode *)
0x1400545d5  mov     ebx, eax
0x1400545d7  test    eax, eax
0x1400545d9  js      short loc_14005460A
0x1400545db  mov     r8, [r13+28h]
0x1400545df  mov     rdx, r12; lpPathName
0x1400545e2  mov     rcx, r13; this
0x1400545e5  mov     r8, [r8+r15*8]; struct Package *
0x1400545e9  call    ?InitializePackage@PackageCollection@@AEAAJPEBGPEAVPackage@@@Z; PackageCollection::InitializePackage(ushort const *,Package *)
0x1400545ee  mov     ebx, eax
0x1400545f0  test    eax, eax
0x1400545f2  js      short loc_1400545FF
0x1400545f4  mov     esi, [rbp+57h+arg_18]
0x1400545f7  add     r15d, edi
0x1400545fa  jmp     loc_140054471
0x1400545ff  mov     r9d, 677h
0x140054605  jmp     loc_14005468D
0x14005460a  mov     r9d, 671h
0x140054610  jmp     short loc_14005468D
0x140054612  mov     r9d, 66Bh
0x140054618  jmp     short loc_14005468D
0x14005461a  mov     r9d, 665h
0x140054620  jmp     short loc_14005468D
0x140054622  mov     r9d, 662h
0x140054628  mov     [rsp+0C0h+var_A0], eax
0x14005462c  lea     r8, aPackagecollect_21; "PackageCollection::LoadConfigFile"
0x140054633  mov     ecx, edi; Level
0x140054635  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x14005463c  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140054641  mov     r12, [rbp+57h+var_50]
0x140054645  jmp     short loc_1400546A6
0x140054647  mov     r9d, 65Fh
0x14005464d  jmp     short loc_14005468D
0x14005464f  mov     r9d, 659h
0x140054655  mov     [rsp+0C0h+var_A0], eax
0x140054659  lea     r8, aPackagecollect_21; "PackageCollection::LoadConfigFile"
0x140054660  mov     ecx, edi; Level
0x140054662  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x140054669  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14005466e  mov     r14, [rbp+57h+lpSrc]
0x140054672  mov     [rbp+57h+var_70], r14
0x140054676  jmp     short loc_1400546A6
0x140054678  mov     r9d, 656h
0x14005467e  jmp     short loc_14005468D
0x140054680  mov     eax, 8007000Eh
0x140054685  mov     r9d, 653h
  ... truncated ...
```
