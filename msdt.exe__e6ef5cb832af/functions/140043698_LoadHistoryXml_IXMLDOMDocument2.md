# LoadHistoryXml(IXMLDOMDocument2 *)

- ea: `0x140043698`
- end: `0x140043a0e`
- name: `?LoadHistoryXml@@YAJPEAUIXMLDOMDocument2@@@Z`
- size: `886`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x140043024`

## callees

- `0x14000706c`
- `0x1400070b0`
- `0x140020420`
- `0x140042858`
- `0x140043698`
- `0x140048c58`
- `0x1400499a8`
- `0x14004a13c`
- `0x14004a1d0`
- `0x14004a244`
- `0x14004a7a8`
- `0x14004a8d8`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1400436c6`
- `KERNEL32!HeapAlloc` at `0x1400436c6`
- `KERNEL32!HeapFree` at `0x1400439ea`
- `KERNEL32!HeapFree` at `0x1400439ea`
- `KERNEL32!GetProcessHeap` at `0x1400436af`
- `KERNEL32!GetProcessHeap` at `0x1400439d6`
- `KERNEL32!GetProcessHeap` at `0x1400436af`
- `KERNEL32!GetProcessHeap` at `0x1400439d6`
- `OLEAUT32!__imp_SysFreeString` at `0x14004397a`
- `OLEAUT32!__imp_SysFreeString` at `0x14004398e`
- `OLEAUT32!__imp_SysFreeString` at `0x1400439a2`
- `OLEAUT32!__imp_SysFreeString` at `0x1400439b6`
- `OLEAUT32!__imp_SysFreeString` at `0x1400439ca`
- `OLEAUT32!__imp_SysFreeString` at `0x14004397a`
- `OLEAUT32!__imp_SysFreeString` at `0x14004398e`
- `OLEAUT32!__imp_SysFreeString` at `0x1400439a2`
- `OLEAUT32!__imp_SysFreeString` at `0x1400439b6`
- `OLEAUT32!__imp_SysFreeString` at `0x1400439ca`

## string_xrefs

- `0x1400436e1`: `LoadHistoryXml`
- `0x14004373d`: `LoadHistoryXml`
- `0x140043915`: `LoadHistoryXml`
- `0x140043952`: `LoadHistoryXml`

## pseudocode

```c
__int64 __fastcall LoadHistoryXml(struct IXMLDOMDocument2 *a1)
{
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v3; // r14
  unsigned int v4; // ebx
  OLECHAR *v5; // r15
  OLECHAR *v6; // rsi
  OLECHAR *v7; // r12
  int appended; // eax
  OLECHAR *v9; // r13
  int v10; // r9d
  unsigned int NumberRootCauses; // eax
  OLECHAR *v12; // rax
  const unsigned __int16 *v13; // rax
  unsigned __int64 v14; // rbp
  OLECHAR *v15; // r8
  unsigned __int64 i; // rsi
  int v17; // eax
  int v18; // eax
  HANDLE v19; // rax
  OLECHAR *v21; // [rsp+78h] [rbp+10h]
  OLECHAR *bstrString; // [rsp+80h] [rbp+18h]

  ProcessHeap = GetProcessHeap();
  v3 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x800u);
  if ( !v3 )
  {
    v4 = -2147024882;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "LoadHistoryXml", 611, -2147024882);
    return v4;
  }
  v5 = 0;
  v6 = 0;
  v7 = 0;
  bstrString = Packages_ID();
  appended = AppendElement(a1, (OLECHAR *)L"ID", bstrString);
  v4 = appended;
  if ( appended >= 0 )
  {
    v9 = Packages_Name();
    appended = AppendElement(a1, (OLECHAR *)L"Name", v9);
    v4 = appended;
    if ( appended >= 0 )
    {
      NumberRootCauses = Packages_GetNumberRootCauses();
      appended = StringCchPrintfW(v3, 0x400u, L"%u", NumberRootCauses);
      v4 = appended;
      if ( appended >= 0 )
      {
        v21 = Packages_Publisher();
        v6 = v21;
        appended = AppendElement(a1, (OLECHAR *)L"Publisher", v21);
        v4 = appended;
        if ( appended >= 0 )
        {
          if ( *((_DWORD *)Config + 3) )
          {
            appended = AppendElement(a1, (OLECHAR *)L"SupportKey", *((OLECHAR **)Config + 14));
            v4 = appended;
            if ( appended < 0 )
            {
              v10 = 636;
              goto LABEL_5;
            }
            appended = AppendElement(a1, (OLECHAR *)L"SupportProvider", *((OLECHAR **)Config + 12));
            v4 = appended;
            if ( appended < 0 )
            {
              v10 = 642;
              goto LABEL_5;
            }
          }
          v12 = (OLECHAR *)Packages_Icon();
          appended = AppendElement(a1, (OLECHAR *)L"Icon", v12);
          v4 = appended;
          if ( appended >= 0 )
          {
            v7 = Packages_Category();
            appended = AppendElement(a1, (OLECHAR *)L"Category", v7);
            v4 = appended;
            if ( appended >= 0 )
            {
              v13 = Packages_Keywords();
              v5 = (OLECHAR *)v13;
              if ( v13 )
              {
                if ( StringCchCopyW(v3, 0x400u, v13) )
                {
                  v4 = 0;
                }
                else
                {
                  v14 = -1;
                  v15 = v3;
                  do
                    ++v14;
                  while ( v3[v14] );
                  for ( i = 0; i < v14; ++i )
                  {
                    if ( v3[i] == 43 )
                    {
                      v3[i] = 0;
                      v17 = AppendElement(a1, (OLECHAR *)L"Keyword", v15);
                      v4 = v17;
                      if ( v17 < 0 )
                      {
                        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "LoadHistoryXml", 685, v17);
                        goto LABEL_35;
                      }
                      v15 = &v3[i + 1];
                    }
                  }
                  v18 = AppendElement(a1, (OLECHAR *)L"Keyword", v15);
                  v4 = v18;
                  if ( v18 < 0 )
                    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "LoadHistoryXml", 692, v18);
LABEL_35:
                  v6 = v21;
                }
              }
              goto LABEL_36;
            }
            v10 = 654;
          }
          else
          {
            v10 = 649;
          }
        }
        else
        {
          v10 = 629;
        }
      }
      else
      {
        v10 = 624;
      }
    }
    else
    {
      v10 = 621;
    }
  }
  else
  {
    v9 = 0;
    v10 = 616;
  }
LABEL_5:
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "LoadHistoryXml", v10, appended);
LABEL_36:
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v9 )
    SysFreeString(v9);
  if ( v6 )
    SysFreeString(v6);
  if ( v5 )
    SysFreeString(v5);
  if ( v7 )
    SysFreeString(v7);
  v19 = GetProcessHeap();
  HeapFree(v19, 0, v3);
  return v4;
}

```

## disassembly

```asm
0x140043698  mov     [rsp+arg_0], rbx
0x14004369d  push    rbp
0x14004369e  push    rsi
0x14004369f  push    rdi
0x1400436a0  push    r12
0x1400436a2  push    r13
0x1400436a4  push    r14
0x1400436a6  push    r15
0x1400436a8  sub     rsp, 30h
0x1400436ac  mov     rdi, rcx
0x1400436af  call    cs:__imp_GetProcessHeap
0x1400436b6  nop     dword ptr [rax+rax+00h]
0x1400436bb  xor     edx, edx; dwFlags
0x1400436bd  mov     r8d, 800h; dwBytes
0x1400436c3  mov     rcx, rax; hHeap
0x1400436c6  call    cs:__imp_HeapAlloc
0x1400436cd  nop     dword ptr [rax+rax+00h]
0x1400436d2  xor     ebp, ebp
0x1400436d4  mov     r14, rax
0x1400436d7  test    rax, rax
0x1400436da  jnz     short loc_140043706
0x1400436dc  mov     ebx, 8007000Eh
0x1400436e1  lea     r8, aLoadhistoryxml; "LoadHistoryXml"
0x1400436e8  mov     r9d, 263h
0x1400436ee  mov     [rsp+68h+var_48], ebx
0x1400436f2  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400436f9  lea     ecx, [rax+1]; Level
0x1400436fc  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140043701  jmp     loc_1400439F6
0x140043706  mov     r15, rbp
0x140043709  mov     rsi, rbp
0x14004370c  mov     r12, rbp
0x14004370f  call    ?Packages_ID@@YAPEAGXZ; Packages_ID(void)
0x140043714  mov     r8, rax; OLECHAR *
0x140043717  mov     [rsp+68h+bstrString], rax
0x14004371f  lea     rdx, aId_0; "ID"
0x140043726  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x140043729  call    ?AppendElement@@YAJPEAUIXMLDOMDocument2@@PEBG1@Z; AppendElement(IXMLDOMDocument2 *,ushort const *,ushort const *)
0x14004372e  mov     ebx, eax
0x140043730  test    eax, eax
0x140043732  jns     short loc_14004375E
0x140043734  mov     r13, rbp
0x140043737  mov     r9d, 268h
0x14004373d  lea     r8, aLoadhistoryxml; "LoadHistoryXml"
0x140043744  mov     [rsp+68h+var_48], eax
0x140043748  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14004374f  mov     ecx, 1; Level
0x140043754  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140043759  jmp     loc_14004396D
0x14004375e  call    ?Packages_Name@@YAPEAGXZ; Packages_Name(void)
0x140043763  mov     r8, rax; OLECHAR *
0x140043766  lea     rdx, aName; "Name"
0x14004376d  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x140043770  mov     r13, rax
0x140043773  call    ?AppendElement@@YAJPEAUIXMLDOMDocument2@@PEBG1@Z; AppendElement(IXMLDOMDocument2 *,ushort const *,ushort const *)
0x140043778  mov     ebx, eax
0x14004377a  test    eax, eax
0x14004377c  jns     short loc_140043786
0x14004377e  mov     r9d, 26Dh
0x140043784  jmp     short loc_14004373D
0x140043786  call    ?Packages_GetNumberRootCauses@@YAIXZ; Packages_GetNumberRootCauses(void)
0x14004378b  mov     r9d, eax
0x14004378e  lea     r8, aU; "%u"
0x140043795  mov     edx, 400h; unsigned __int64
0x14004379a  mov     rcx, r14; unsigned __int16 *
0x14004379d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400437a2  mov     ebx, eax
0x1400437a4  test    eax, eax
0x1400437a6  jns     short loc_1400437B0
0x1400437a8  mov     r9d, 270h
0x1400437ae  jmp     short loc_14004373D
0x1400437b0  call    ?Packages_Publisher@@YAPEAGXZ; Packages_Publisher(void)
0x1400437b5  mov     r8, rax; OLECHAR *
0x1400437b8  mov     [rsp+68h+arg_8], rax
0x1400437bd  lea     rdx, aPublisher; "Publisher"
0x1400437c4  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x1400437c7  mov     rsi, rax
0x1400437ca  call    ?AppendElement@@YAJPEAUIXMLDOMDocument2@@PEBG1@Z; AppendElement(IXMLDOMDocument2 *,ushort const *,ushort const *)
0x1400437cf  mov     ebx, eax
0x1400437d1  test    eax, eax
0x1400437d3  jns     short loc_1400437E0
0x1400437d5  mov     r9d, 275h
0x1400437db  jmp     loc_14004373D
0x1400437e0  mov     r8, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x1400437e7  cmp     [r8+0Ch], ebp
0x1400437eb  jz      short loc_14004383C
0x1400437ed  mov     r8, [r8+70h]; OLECHAR *
0x1400437f1  lea     rdx, aSupportkey; "SupportKey"
0x1400437f8  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x1400437fb  call    ?AppendElement@@YAJPEAUIXMLDOMDocument2@@PEBG1@Z; AppendElement(IXMLDOMDocument2 *,ushort const *,ushort const *)
0x140043800  mov     ebx, eax
0x140043802  test    eax, eax
0x140043804  jns     short loc_140043811
0x140043806  mov     r9d, 27Ch
0x14004380c  jmp     loc_14004373D
0x140043811  mov     r8, cs:?Config@@3PEAVConfiguration@@EA; Configuration * Config
0x140043818  lea     rdx, aSupportprovide; "SupportProvider"
0x14004381f  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x140043822  mov     r8, [r8+60h]; OLECHAR *
0x140043826  call    ?AppendElement@@YAJPEAUIXMLDOMDocument2@@PEBG1@Z; AppendElement(IXMLDOMDocument2 *,ushort const *,ushort const *)
0x14004382b  mov     ebx, eax
0x14004382d  test    eax, eax
0x14004382f  jns     short loc_14004383C
0x140043831  mov     r9d, 282h
0x140043837  jmp     loc_14004373D
0x14004383c  call    ?Packages_Icon@@YAPEBGXZ; Packages_Icon(void)
0x140043841  mov     r8, rax; OLECHAR *
0x140043844  lea     rdx, aIcon; "Icon"
0x14004384b  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x14004384e  call    ?AppendElement@@YAJPEAUIXMLDOMDocument2@@PEBG1@Z; AppendElement(IXMLDOMDocument2 *,ushort const *,ushort const *)
0x140043853  mov     ebx, eax
0x140043855  test    eax, eax
0x140043857  jns     short loc_140043864
0x140043859  mov     r9d, 289h
0x14004385f  jmp     loc_14004373D
0x140043864  call    ?Packages_Category@@YAPEAGXZ; Packages_Category(void)
0x140043869  mov     r8, rax; OLECHAR *
0x14004386c  lea     rdx, aCategory; "Category"
0x140043873  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x140043876  mov     r12, rax
0x140043879  call    ?AppendElement@@YAJPEAUIXMLDOMDocument2@@PEBG1@Z; AppendElement(IXMLDOMDocument2 *,ushort const *,ushort const *)
0x14004387e  mov     ebx, eax
0x140043880  test    eax, eax
0x140043882  jns     short loc_14004388F
0x140043884  mov     r9d, 28Eh
0x14004388a  jmp     loc_14004373D
0x14004388f  call    ?Packages_Keywords@@YAPEAGXZ; Packages_Keywords(void)
0x140043894  mov     r15, rax
0x140043897  test    rax, rax
0x14004389a  jz      loc_14004396D
0x1400438a0  mov     r8, rax; unsigned __int16 *
0x1400438a3  mov     edx, 400h; unsigned __int64
0x1400438a8  mov     rcx, r14; unsigned __int16 *
0x1400438ab  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400438b0  test    eax, eax
0x1400438b2  jz      short loc_1400438BB
0x1400438b4  mov     ebx, ebp
0x1400438b6  jmp     loc_14004396D
0x1400438bb  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1400438bf  mov     r8, r14; OLECHAR *
0x1400438c2  xor     ecx, ecx
0x1400438c4  inc     rbp
0x1400438c7  cmp     [r14+rbp*2], cx
0x1400438cc  jnz     short loc_1400438C4
0x1400438ce  mov     rsi, rcx
0x1400438d1  cmp     rsi, rbp
0x1400438d4  jnb     short loc_140043931
0x1400438d6  mov     eax, 2Bh ; '+'
0x1400438db  cmp     ax, [r14+rsi*2]
0x1400438e0  jnz     short loc_140043906
0x1400438e2  mov     [r14+rsi*2], cx
0x1400438e7  lea     rdx, aKeyword; "Keyword"
0x1400438ee  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x1400438f1  call    ?AppendElement@@YAJPEAUIXMLDOMDocument2@@PEBG1@Z; AppendElement(IXMLDOMDocument2 *,ushort const *,ushort const *)
0x1400438f6  xor     ecx, ecx
0x1400438f8  mov     ebx, eax
0x1400438fa  test    eax, eax
0x1400438fc  js      short loc_14004390B
0x1400438fe  lea     r8, [r14+2]
0x140043902  lea     r8, [r8+rsi*2]
0x140043906  inc     rsi
0x140043909  jmp     short loc_1400438D1
0x14004390b  mov     r9d, 2ADh
0x140043911  mov     [rsp+68h+var_48], eax
0x140043915  lea     r8, aLoadhistoryxml; "LoadHistoryXml"
0x14004391c  mov     ecx, 1; Level
0x140043921  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140043928  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14004392d  xor     ebp, ebp
0x14004392f  jmp     short loc_140043968
0x140043931  lea     rdx, aKeyword; "Keyword"
0x140043938  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x14004393b  call    ?AppendElement@@YAJPEAUIXMLDOMDocument2@@PEBG1@Z; AppendElement(IXMLDOMDocument2 *,ushort const *,ushort const *)
0x140043940  xor     ebp, ebp
0x140043942  mov     ebx, eax
0x140043944  test    eax, eax
0x140043946  jns     short loc_140043968
0x140043948  mov     r9d, 2B4h
0x14004394e  mov     [rsp+68h+var_48], eax
0x140043952  lea     r8, aLoadhistoryxml; "LoadHistoryXml"
0x140043959  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140043960  lea     ecx, [rbp+1]; Level
0x140043963  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140043968  mov     rsi, [rsp+68h+arg_8]
0x14004396d  mov     rcx, [rsp+68h+bstrString]; bstrString
0x140043975  test    rcx, rcx
0x140043978  jz      short loc_140043986
0x14004397a  call    cs:__imp_SysFreeString
0x140043981  nop     dword ptr [rax+rax+00h]
0x140043986  test    r13, r13
0x140043989  jz      short loc_14004399A
0x14004398b  mov     rcx, r13; bstrString
0x14004398e  call    cs:__imp_SysFreeString
0x140043995  nop     dword ptr [rax+rax+00h]
0x14004399a  test    rsi, rsi
0x14004399d  jz      short loc_1400439AE
0x14004399f  mov     rcx, rsi; bstrString
0x1400439a2  call    cs:__imp_SysFreeString
0x1400439a9  nop     dword ptr [rax+rax+00h]
0x1400439ae  test    r15, r15
0x1400439b1  jz      short loc_1400439C2
0x1400439b3  mov     rcx, r15; bstrString
0x1400439b6  call    cs:__imp_SysFreeString
0x1400439bd  nop     dword ptr [rax+rax+00h]
0x1400439c2  test    r12, r12
0x1400439c5  jz      short loc_1400439D6
0x1400439c7  mov     rcx, r12; bstrString
0x1400439ca  call    cs:__imp_SysFreeString
0x1400439d1  nop     dword ptr [rax+rax+00h]
0x1400439d6  call    cs:__imp_GetProcessHeap
0x1400439dd  nop     dword ptr [rax+rax+00h]
0x1400439e2  mov     r8, r14; lpMem
0x1400439e5  xor     edx, edx; dwFlags
0x1400439e7  mov     rcx, rax; hHeap
0x1400439ea  call    cs:__imp_HeapFree
0x1400439f1  nop     dword ptr [rax+rax+00h]
0x1400439f6  mov     eax, ebx
0x1400439f8  mov     rbx, [rsp+68h+arg_0]
0x1400439fd  add     rsp, 30h
0x140043a01  pop     r15
0x140043a03  pop     r14
0x140043a05  pop     r13
0x140043a07  pop     r12
0x140043a09  pop     rdi
0x140043a0a  pop     rsi
0x140043a0b  pop     rbp
0x140043a0c  retn
```
