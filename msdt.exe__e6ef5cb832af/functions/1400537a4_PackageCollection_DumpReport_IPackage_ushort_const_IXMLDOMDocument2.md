# PackageCollection::DumpReport(IPackage *,ushort const *,IXMLDOMDocument2 * *)

- ea: `0x1400537a4`
- end: `0x140053ba4`
- name: `?DumpReport@PackageCollection@@AEAAJPEAVIPackage@@PEBGPEAPEAUIXMLDOMDocument2@@@Z`
- size: `1024`
- prototype: `__int64 __fastcall(PackageCollection *this, struct IPackage *, const unsigned __int16 *, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x1400556c0`

## callees

- `0x140006fe0`
- `0x14000706c`
- `0x1400070b0`
- `0x140020420`
- `0x140021f70`
- `0x1400537a4`
- `0x140056714`
- `0x14005c8d8`
- `0x140063010`

## import_xrefs

- `KERNEL32!MoveFileW` at `0x140053a4a`
- `KERNEL32!MoveFileW` at `0x140053a4a`
- `KERNEL32!GetLastError` at `0x140053a5a`
- `KERNEL32!GetLastError` at `0x140053a5a`
- `KERNEL32!HeapAlloc` at `0x1400537f4`
- `KERNEL32!HeapAlloc` at `0x140053831`
- `KERNEL32!HeapAlloc` at `0x1400537f4`
- `KERNEL32!HeapAlloc` at `0x140053831`
- `KERNEL32!HeapFree` at `0x140053b5f`
- `KERNEL32!HeapFree` at `0x140053b84`
- `KERNEL32!HeapFree` at `0x140053b5f`
- `KERNEL32!HeapFree` at `0x140053b84`
- `KERNEL32!GetProcessHeap` at `0x1400537da`
- `KERNEL32!GetProcessHeap` at `0x14005381d`
- `KERNEL32!GetProcessHeap` at `0x140053b4b`
- `KERNEL32!GetProcessHeap` at `0x140053b70`
- `KERNEL32!GetProcessHeap` at `0x1400537da`
- `KERNEL32!GetProcessHeap` at `0x14005381d`
- `KERNEL32!GetProcessHeap` at `0x140053b4b`
- `KERNEL32!GetProcessHeap` at `0x140053b70`
- `KERNEL32!DeleteFileW` at `0x140053a38`
- `KERNEL32!DeleteFileW` at `0x140053a38`
- `OLEAUT32!__imp_SysFreeString` at `0x140053b1d`
- `OLEAUT32!__imp_SysFreeString` at `0x140053b36`
- `OLEAUT32!__imp_SysFreeString` at `0x140053b1d`
- `OLEAUT32!__imp_SysFreeString` at `0x140053b36`

## string_xrefs

- `0x140053a85`: `resultreport.xml`
- `0x1400539b5`: `%s%udebugreport.xml`
- `0x1400539e9`: `%s%s.debugreport.xml`
- `0x140053a10`: `debugreport.xml`

## pseudocode

```c
__int64 __fastcall PackageCollection::DumpReport(
        PackageCollection *this,
        struct IPackage *a2,
        const unsigned __int16 *a3,
        struct IXMLDOMDocument2 **a4)
{
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v8; // rdi
  int v9; // eax
  unsigned __int16 *v10; // r14
  signed int v11; // ebx
  int v12; // r9d
  HANDLE v13; // rax
  unsigned __int64 v14; // r11
  unsigned __int64 v15; // rsi
  __int64 v16; // r15
  signed int LastError; // eax
  HANDLE v18; // rax
  HANDLE v19; // rax
  __int64 v21; // [rsp+30h] [rbp-28h] BYREF
  __int64 v22; // [rsp+38h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-18h] BYREF
  BSTR v24[2]; // [rsp+48h] [rbp-10h] BYREF
  unsigned int v25; // [rsp+A0h] [rbp+48h] BYREF
  int v26; // [rsp+A4h] [rbp+4Ch]

  v26 = HIDWORD(this);
  bstrString = 0;
  v24[0] = 0;
  v21 = 0;
  v22 = 0;
  v25 = 0;
  ProcessHeap = GetProcessHeap();
  v8 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x208u);
  if ( v8 )
  {
    v13 = GetProcessHeap();
    v10 = (unsigned __int16 *)HeapAlloc(v13, 0, 0x208u);
    if ( v10 )
    {
      v9 = StringCchCopyW(v8, 0x104u, a3);
      v11 = v9;
      if ( v9 >= 0 )
      {
        v9 = StringCchCatW(v8, v14, L"\\");
        v11 = v9;
        if ( v9 >= 0 )
        {
          v15 = -1;
          v16 = -1;
          do
            ++v16;
          while ( v8[v16] );
          v9 = (*(__int64 (__fastcall **)(struct IPackage *, __int64 *))(*(_QWORD *)a2 + 96LL))(a2, &v21);
          v11 = v9;
          if ( v9 >= 0 )
          {
            v9 = (*(__int64 (__fastcall **)(struct IPackage *, __int64 *))(*(_QWORD *)a2 + 88LL))(a2, &v22);
            v11 = v9;
            if ( v9 >= 0 )
            {
              v9 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v22 + 24LL))(v22, v24);
              v11 = v9;
              if ( v9 >= 0 )
              {
                v9 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v21 + 176LL))(v21, &bstrString);
                v11 = v9;
                if ( v9 >= 0 )
                {
                  v9 = MetCopyDir(v8, bstrString);
                  v11 = v9;
                  if ( v9 >= 0 )
                  {
                    do
                      ++v15;
                    while ( v24[0][v15] );
                    if ( v15 <= 0x20 )
                    {
                      v9 = StringCchPrintfW(v10, 0x104u, L"%s%s.debugreport.xml", v8, v24[0]);
                      v11 = v9;
                      if ( v9 < 0 )
                      {
                        v12 = 2150;
                        goto LABEL_40;
                      }
                    }
                    else
                    {
                      v9 = HashString(v24[0], &v25);
                      v11 = v9;
                      if ( v9 < 0 )
                      {
                        v12 = 2131;
                        goto LABEL_40;
                      }
                      v9 = StringCchPrintfW(v10, 0x104u, L"%s%udebugreport.xml", v8, v25);
                      v11 = v9;
                      if ( v9 < 0 )
                      {
                        v12 = 2139;
                        goto LABEL_40;
                      }
                    }
                    v9 = StringCchCatW(v8, 0x104u, L"debugreport.xml");
                    v11 = v9;
                    if ( v9 >= 0 )
                    {
                      DeleteFileW(v10);
                      if ( !MoveFileW(v8, v10) )
                      {
                        LastError = GetLastError();
                        v11 = LastError;
                        if ( LastError > 0 )
                          v11 = (unsigned __int16)LastError | 0x80070000;
                        if ( v11 < 0 )
                        {
                          SdpDebugPrint(
                            1u,
                            "Met ERROR: %s:%d - hr = 0x%08X\n",
                            "PackageCollection::DumpReport",
                            2159,
                            v11);
                          goto LABEL_41;
                        }
                      }
                      v8[v16] = 0;
                      v9 = StringCchCatW(v8, 0x104u, L"resultreport.xml");
                      v11 = v9;
                      if ( v9 >= 0 )
                      {
                        v9 = AddReportToMetaReport(a2, a4, v8);
                        v11 = v9;
                        if ( v9 >= 0 )
                          goto LABEL_41;
                        v12 = 2173;
                      }
                      else
                      {
                        v12 = 2167;
                      }
                    }
                    else
                    {
                      v12 = 2154;
                    }
                  }
                  else
                  {
                    v12 = 2123;
                  }
                }
                else
                {
                  v12 = 2117;
                }
              }
              else
              {
                v12 = 2114;
              }
            }
            else
            {
              v12 = 2111;
            }
          }
          else
          {
            v12 = 2108;
          }
        }
        else
        {
          v12 = 2103;
        }
      }
      else
      {
        v12 = 2100;
      }
    }
    else
    {
      v9 = -2147024882;
      v12 = 2097;
      v11 = -2147024882;
    }
  }
  else
  {
    v9 = -2147024882;
    v10 = 0;
    v11 = -2147024882;
    v12 = 2096;
  }
LABEL_40:
  SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::DumpReport", v12, v9);
LABEL_41:
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v24[0] )
  {
    SysFreeString(v24[0]);
    v24[0] = 0;
  }
  if ( v10 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v10);
  }
  if ( v8 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v8);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400537a4  mov     qword ptr [rsp-40h+arg_0], rcx
0x1400537a9  push    rbp
0x1400537aa  push    rbx
0x1400537ab  push    rsi
0x1400537ac  push    rdi
0x1400537ad  push    r12
0x1400537af  push    r13
0x1400537b1  push    r14
0x1400537b3  push    r15
0x1400537b5  mov     rbp, rsp
0x1400537b8  sub     rsp, 58h
0x1400537bc  xor     esi, esi
0x1400537be  mov     r13, r9
0x1400537c1  mov     [rbp+bstrString], rsi
0x1400537c5  mov     rbx, r8
0x1400537c8  mov     [rbp+var_10], rsi
0x1400537cc  mov     r12, rdx
0x1400537cf  mov     [rbp+var_28], rsi
0x1400537d3  mov     [rbp+var_20], rsi
0x1400537d7  mov     [rbp+arg_0], esi
0x1400537da  call    cs:__imp_GetProcessHeap
0x1400537e1  nop     dword ptr [rax+rax+00h]
0x1400537e6  mov     r14d, 208h
0x1400537ec  xor     edx, edx; dwFlags
0x1400537ee  mov     rcx, rax; hHeap
0x1400537f1  mov     r8d, r14d; dwBytes
0x1400537f4  call    cs:__imp_HeapAlloc
0x1400537fb  nop     dword ptr [rax+rax+00h]
0x140053800  mov     rdi, rax
0x140053803  test    rax, rax
0x140053806  jnz     short loc_14005381D
0x140053808  mov     eax, 8007000Eh
0x14005380d  mov     r14d, esi
0x140053810  mov     ebx, eax
0x140053812  mov     r9d, 830h
0x140053818  jmp     loc_140053AC6
0x14005381d  call    cs:__imp_GetProcessHeap
0x140053824  nop     dword ptr [rax+rax+00h]
0x140053829  mov     r8, r14; dwBytes
0x14005382c  xor     edx, edx; dwFlags
0x14005382e  mov     rcx, rax; hHeap
0x140053831  call    cs:__imp_HeapAlloc
0x140053838  nop     dword ptr [rax+rax+00h]
0x14005383d  mov     r14, rax
0x140053840  test    rax, rax
0x140053843  jnz     short loc_140053857
0x140053845  mov     eax, 8007000Eh
0x14005384a  mov     r9d, 831h
0x140053850  mov     ebx, eax
0x140053852  jmp     loc_140053AC6
0x140053857  mov     r11d, 104h
0x14005385d  mov     r8, rbx; unsigned __int16 *
0x140053860  mov     edx, r11d; unsigned __int64
0x140053863  mov     rcx, rdi; unsigned __int16 *
0x140053866  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14005386b  mov     ebx, eax
0x14005386d  test    eax, eax
0x14005386f  jns     short loc_14005387C
0x140053871  mov     r9d, 834h
0x140053877  jmp     loc_140053AC6
0x14005387c  lea     r8, asc_14006B250; "\\"
0x140053883  mov     rdx, r11; unsigned __int64
0x140053886  mov     rcx, rdi; unsigned __int16 *
0x140053889  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14005388e  mov     ebx, eax
0x140053890  test    eax, eax
0x140053892  jns     short loc_14005389F
0x140053894  mov     r9d, 837h
0x14005389a  jmp     loc_140053AC6
0x14005389f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1400538a3  mov     r15, rsi
0x1400538a6  xor     eax, eax
0x1400538a8  inc     r15
0x1400538ab  cmp     [rdi+r15*2], ax
0x1400538b0  jnz     short loc_1400538A8
0x1400538b2  mov     rax, [r12]
0x1400538b6  lea     rdx, [rbp+var_28]
0x1400538ba  mov     rcx, r12
0x1400538bd  mov     rax, [rax+60h]
0x1400538c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400538c6  mov     ebx, eax
0x1400538c8  test    eax, eax
0x1400538ca  jns     short loc_1400538F5
0x1400538cc  mov     r9d, 83Ch
0x1400538d2  lea     r8, aPackagecollect_12; "PackageCollection::DumpReport"
0x1400538d9  mov     dword ptr [rsp+58h+var_38], eax
0x1400538dd  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x1400538e4  mov     ecx, 1; Level
0x1400538e9  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400538ee  xor     esi, esi
0x1400538f0  jmp     loc_140053AE2
0x1400538f5  mov     rax, [r12]
0x1400538f9  lea     rdx, [rbp+var_20]
0x1400538fd  mov     rcx, r12
0x140053900  mov     rax, [rax+58h]
0x140053904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053909  mov     ebx, eax
0x14005390b  test    eax, eax
0x14005390d  jns     short loc_140053917
0x14005390f  mov     r9d, 83Fh
0x140053915  jmp     short loc_1400538D2
0x140053917  mov     rcx, [rbp+var_20]
0x14005391b  lea     rdx, [rbp+var_10]
0x14005391f  mov     rax, [rcx]
0x140053922  mov     rax, [rax+18h]
0x140053926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005392b  mov     ebx, eax
0x14005392d  test    eax, eax
0x14005392f  jns     short loc_140053939
0x140053931  mov     r9d, 842h
0x140053937  jmp     short loc_1400538D2
0x140053939  mov     rcx, [rbp+var_28]
0x14005393d  lea     rdx, [rbp+bstrString]
0x140053941  mov     rax, [rcx]
0x140053944  mov     rax, [rax+0B0h]
0x14005394b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053950  mov     ebx, eax
0x140053952  test    eax, eax
0x140053954  jns     short loc_140053961
0x140053956  mov     r9d, 845h
0x14005395c  jmp     loc_1400538D2
0x140053961  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x140053965  mov     rcx, rdi; unsigned __int16 *
0x140053968  call    ?MetCopyDir@@YAJPEBG0@Z; MetCopyDir(ushort const *,ushort const *)
0x14005396d  xor     ecx, ecx
0x14005396f  mov     ebx, eax
0x140053971  test    eax, eax
0x140053973  jns     short loc_140053980
0x140053975  mov     r9d, 84Bh
0x14005397b  jmp     loc_1400538D2
0x140053980  mov     rax, [rbp+var_10]
0x140053984  inc     rsi
0x140053987  cmp     [rax+rsi*2], cx
0x14005398b  jnz     short loc_140053984
0x14005398d  cmp     rsi, 20h ; ' '
0x140053991  jbe     short loc_1400539E1
0x140053993  lea     rdx, [rbp+arg_0]; unsigned int *
0x140053997  mov     rcx, rax; unsigned __int16 *
0x14005399a  call    ?HashString@@YAJPEBGPEAK@Z; HashString(ushort const *,ulong *)
0x14005399f  xor     esi, esi
0x1400539a1  mov     ebx, eax
0x1400539a3  test    eax, eax
0x1400539a5  jns     short loc_1400539B2
0x1400539a7  mov     r9d, 853h
0x1400539ad  jmp     loc_140053AC6
0x1400539b2  mov     eax, [rbp+arg_0]
0x1400539b5  lea     r8, aSUdebugreportX; "%s%udebugreport.xml"
0x1400539bc  mov     r9, rdi
0x1400539bf  mov     dword ptr [rsp+58h+var_38], eax
0x1400539c3  mov     edx, 104h; unsigned __int64
0x1400539c8  mov     rcx, r14; unsigned __int16 *
0x1400539cb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400539d0  mov     ebx, eax
0x1400539d2  test    eax, eax
0x1400539d4  jns     short loc_140053A10
0x1400539d6  mov     r9d, 85Bh
0x1400539dc  jmp     loc_140053AC6
0x1400539e1  mov     r9, rdi
0x1400539e4  mov     [rsp+58h+var_38], rax
0x1400539e9  lea     r8, aSSDebugreportX; "%s%s.debugreport.xml"
0x1400539f0  mov     edx, 104h; unsigned __int64
0x1400539f5  mov     rcx, r14; unsigned __int16 *
0x1400539f8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400539fd  xor     esi, esi
0x1400539ff  mov     ebx, eax
0x140053a01  test    eax, eax
0x140053a03  jns     short loc_140053A10
0x140053a05  mov     r9d, 866h
0x140053a0b  jmp     loc_140053AC6
0x140053a10  lea     r8, aDebugreportXml; "debugreport.xml"
0x140053a17  mov     edx, 104h; unsigned __int64
0x140053a1c  mov     rcx, rdi; unsigned __int16 *
0x140053a1f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140053a24  mov     ebx, eax
0x140053a26  test    eax, eax
0x140053a28  jns     short loc_140053A35
0x140053a2a  mov     r9d, 86Ah
0x140053a30  jmp     loc_140053AC6
0x140053a35  mov     rcx, r14; lpFileName
0x140053a38  call    cs:__imp_DeleteFileW
0x140053a3f  nop     dword ptr [rax+rax+00h]
0x140053a44  mov     rdx, r14; lpNewFileName
0x140053a47  mov     rcx, rdi; lpExistingFileName
0x140053a4a  call    cs:__imp_MoveFileW
0x140053a51  nop     dword ptr [rax+rax+00h]
0x140053a56  test    eax, eax
0x140053a58  jnz     short loc_140053A85
0x140053a5a  call    cs:__imp_GetLastError
0x140053a61  nop     dword ptr [rax+rax+00h]
0x140053a66  mov     ebx, eax
0x140053a68  test    eax, eax
0x140053a6a  jle     short loc_140053A75
0x140053a6c  movzx   ebx, ax
0x140053a6f  or      ebx, 80070000h
0x140053a75  test    ebx, ebx
0x140053a77  jns     short loc_140053A85
0x140053a79  mov     dword ptr [rsp+58h+var_38], ebx
0x140053a7d  mov     r9d, 86Fh
0x140053a83  jmp     short loc_140053ACA
0x140053a85  lea     r8, aResultreportXm; "resultreport.xml"
0x140053a8c  mov     [rdi+r15*2], si
0x140053a91  mov     edx, 104h; unsigned __int64
0x140053a96  mov     rcx, rdi; unsigned __int16 *
0x140053a99  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140053a9e  mov     ebx, eax
0x140053aa0  test    eax, eax
0x140053aa2  jns     short loc_140053AAC
0x140053aa4  mov     r9d, 877h
0x140053aaa  jmp     short loc_140053AC6
0x140053aac  mov     r8, rdi; unsigned __int16 *
0x140053aaf  mov     rdx, r13; struct IXMLDOMDocument2 **
0x140053ab2  mov     rcx, r12; struct Package *
0x140053ab5  call    ?AddReportToMetaReport@@YAJPEAVPackage@@PEAPEAUIXMLDOMDocument2@@PEAG@Z; AddReportToMetaReport(Package *,IXMLDOMDocument2 * *,ushort *)
0x140053aba  mov     ebx, eax
0x140053abc  test    eax, eax
0x140053abe  jns     short loc_140053AE2
0x140053ac0  mov     r9d, 87Dh
0x140053ac6  mov     dword ptr [rsp+58h+var_38], eax
0x140053aca  lea     r8, aPackagecollect_12; "PackageCollection::DumpReport"
0x140053ad1  mov     ecx, 1; Level
0x140053ad6  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x140053add  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140053ae2  mov     rcx, [rbp+var_28]
0x140053ae6  test    rcx, rcx
0x140053ae9  jz      short loc_140053AFB
0x140053aeb  mov     rax, [rcx]
0x140053aee  mov     rax, [rax+10h]
0x140053af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053af7  mov     [rbp+var_28], rsi
0x140053afb  mov     rcx, [rbp+var_20]
0x140053aff  test    rcx, rcx
0x140053b02  jz      short loc_140053B14
0x140053b04  mov     rax, [rcx]
0x140053b07  mov     rax, [rax+10h]
0x140053b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053b10  mov     [rbp+var_20], rsi
0x140053b14  mov     rcx, [rbp+bstrString]; bstrString
0x140053b18  test    rcx, rcx
0x140053b1b  jz      short loc_140053B2D
0x140053b1d  call    cs:__imp_SysFreeString
0x140053b24  nop     dword ptr [rax+rax+00h]
0x140053b29  mov     [rbp+bstrString], rsi
0x140053b2d  mov     rcx, [rbp+var_10]; bstrString
0x140053b31  test    rcx, rcx
0x140053b34  jz      short loc_140053B46
0x140053b36  call    cs:__imp_SysFreeString
0x140053b3d  nop     dword ptr [rax+rax+00h]
0x140053b42  mov     [rbp+var_10], rsi
0x140053b46  test    r14, r14
0x140053b49  jz      short loc_140053B6B
0x140053b4b  call    cs:__imp_GetProcessHeap
0x140053b52  nop     dword ptr [rax+rax+00h]
0x140053b57  mov     r8, r14; lpMem
0x140053b5a  xor     edx, edx; dwFlags
0x140053b5c  mov     rcx, rax; hHeap
0x140053b5f  call    cs:__imp_HeapFree
0x140053b66  nop     dword ptr [rax+rax+00h]
0x140053b6b  test    rdi, rdi
0x140053b6e  jz      short loc_140053B90
0x140053b70  call    cs:__imp_GetProcessHeap
0x140053b77  nop     dword ptr [rax+rax+00h]
0x140053b7c  mov     r8, rdi; lpMem
0x140053b7f  xor     edx, edx; dwFlags
0x140053b81  mov     rcx, rax; hHeap
0x140053b84  call    cs:__imp_HeapFree
0x140053b8b  nop     dword ptr [rax+rax+00h]
0x140053b90  mov     eax, ebx
0x140053b92  add     rsp, 58h
0x140053b96  pop     r15
0x140053b98  pop     r14
0x140053b9a  pop     r13
0x140053b9c  pop     r12
0x140053b9e  pop     rdi
0x140053b9f  pop     rsi
0x140053ba0  pop     rbx
0x140053ba1  pop     rbp
0x140053ba2  retn
```
