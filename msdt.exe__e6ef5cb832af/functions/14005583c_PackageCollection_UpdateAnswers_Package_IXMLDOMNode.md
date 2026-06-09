# PackageCollection::UpdateAnswers(Package *,IXMLDOMNode *)

- ea: `0x14005583c`
- end: `0x140055a59`
- name: `?UpdateAnswers@PackageCollection@@QEAAJPEAVPackage@@PEAUIXMLDOMNode@@@Z`
- size: `541`
- prototype: `__int64 __fastcall(PackageCollection *this, struct Package *, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x140057954`

## callees

- `0x140020420`
- `0x14005583c`
- `0x1400583b0`
- `0x1400596a4`
- `0x140059c4c`
- `0x14005c390`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140055961`
- `KERNEL32!HeapFree` at `0x140055a30`
- `KERNEL32!HeapFree` at `0x140055961`
- `KERNEL32!HeapFree` at `0x140055a30`
- `KERNEL32!GetProcessHeap` at `0x14005594d`
- `KERNEL32!GetProcessHeap` at `0x140055a1c`
- `KERNEL32!GetProcessHeap` at `0x14005594d`
- `KERNEL32!GetProcessHeap` at `0x140055a1c`
- `OLEAUT32!__imp_SysFreeString` at `0x140055935`
- `OLEAUT32!__imp_SysFreeString` at `0x140055a0b`
- `OLEAUT32!__imp_SysFreeString` at `0x140055935`
- `OLEAUT32!__imp_SysFreeString` at `0x140055a0b`

## string_xrefs

- `0x14005587a`: `PackageCollection::UpdateAnswers`
- `0x140055996`: `PackageCollection::UpdateAnswers`
- `0x1400559c2`: `PackageCollection::UpdateAnswers`
- `0x1400559e7`: `PackageCollection::UpdateAnswers`

## pseudocode

```c
__int64 __fastcall PackageCollection::UpdateAnswers(
        PackageCollection *this,
        struct Package *a2,
        struct IXMLDOMNode *a3)
{
  unsigned __int16 *v3; // rbp
  OLECHAR *v4; // rdi
  int v7; // r9d
  unsigned int v8; // ebx
  __int64 i; // r14
  __int64 v10; // rax
  Package *v11; // r15
  int v12; // eax
  int Answers; // eax
  int v14; // eax
  HANDLE ProcessHeap; // rax
  int v16; // r9d
  HANDLE v17; // rax
  BSTR bstrString; // [rsp+30h] [rbp-38h] BYREF
  struct Package *v20; // [rsp+78h] [rbp+10h]
  unsigned __int16 *v21; // [rsp+88h] [rbp+20h] BYREF

  v20 = a2;
  v3 = 0;
  v4 = 0;
  v21 = 0;
  bstrString = 0;
  if ( !a2 )
  {
    v7 = 1944;
LABEL_3:
    v8 = -2147024809;
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::UpdateAnswers", v7, -2147024809);
    return v8;
  }
  if ( !a3 )
  {
    v7 = 1945;
    goto LABEL_3;
  }
  v8 = 0;
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 9); i = (unsigned int)(i + 1) )
  {
    v10 = *((_QWORD *)this + 5);
    v11 = *(Package **)(v10 + 8 * i);
    if ( v11 != a2 )
    {
      v12 = Package::MarkPrereqs(*(Package **)(v10 + 8 * i), a3);
      v8 = v12;
      if ( v12 < 0 )
      {
        v16 = 1961;
        goto LABEL_23;
      }
      Answers = Package::get_Answers(v11, &bstrString);
      v8 = Answers;
      if ( Answers < 0 )
      {
        SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::UpdateAnswers", 1964, Answers);
        v4 = bstrString;
        break;
      }
      v4 = bstrString;
      if ( bstrString )
      {
        v14 = MetSubstituteXmlParameters(&v21, bstrString, a3);
        v8 = v14;
        if ( v14 < 0 )
        {
          SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::UpdateAnswers", 1971, v14);
          v3 = v21;
          break;
        }
        v3 = v21;
        v12 = Package::set_Answers(v11, v21);
        v8 = v12;
        if ( v12 < 0 )
        {
          v16 = 1974;
LABEL_23:
          SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::UpdateAnswers", v16, v12);
          break;
        }
        SysFreeString(v4);
        v4 = 0;
        bstrString = 0;
      }
      if ( v3 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v3);
        v3 = 0;
        v21 = 0;
      }
      a2 = v20;
    }
  }
  if ( v4 )
    SysFreeString(v4);
  if ( v3 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v3);
  }
  return v8;
}

```

## disassembly

```asm
0x14005583c  mov     rax, rsp
0x14005583f  mov     [rax+8], rbx
0x140055843  mov     [rax+18h], rbp
0x140055847  mov     [rax+10h], rdx
0x14005584b  push    rdi
0x14005584c  push    r12
0x14005584e  push    r13
0x140055850  push    r14
0x140055852  push    r15
0x140055854  sub     rsp, 40h
0x140055858  xor     ebp, ebp
0x14005585a  xor     edi, edi
0x14005585c  mov     [rax+20h], rbp
0x140055860  mov     r12, r8
0x140055863  mov     [rax-38h], rdi
0x140055867  mov     r13, rcx
0x14005586a  test    rdx, rdx
0x14005586d  jnz     short loc_14005589D
0x14005586f  mov     r9d, 798h
0x140055875  mov     eax, 80070057h
0x14005587a  lea     r8, aPackagecollect_11; "PackageCollection::UpdateAnswers"
0x140055881  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x140055888  mov     [rsp+68h+var_48], eax
0x14005588c  mov     ecx, 1; Level
0x140055891  mov     ebx, eax
0x140055893  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140055898  jmp     loc_140055A3C
0x14005589d  test    r12, r12
0x1400558a0  jnz     short loc_1400558AA
0x1400558a2  mov     r9d, 799h
0x1400558a8  jmp     short loc_140055875
0x1400558aa  xor     ebx, ebx
0x1400558ac  xor     r14d, r14d
0x1400558af  cmp     r14d, [r13+24h]
0x1400558b3  jnb     loc_140055A03
0x1400558b9  mov     rax, [r13+28h]
0x1400558bd  mov     r15, [rax+r14*8]
0x1400558c1  cmp     r15, rdx
0x1400558c4  jz      loc_14005597C
0x1400558ca  mov     rdx, r12; struct IXMLDOMNode *
0x1400558cd  mov     rcx, r15; this
0x1400558d0  call    ?MarkPrereqs@Package@@QEAAJPEAUIXMLDOMNode@@@Z; Package::MarkPrereqs(IXMLDOMNode *)
0x1400558d5  mov     ebx, eax
0x1400558d7  test    eax, eax
0x1400558d9  js      loc_1400559E1
0x1400558df  lea     rdx, [rsp+68h+bstrString]; unsigned __int16 **
0x1400558e4  mov     rcx, r15; this
0x1400558e7  call    ?get_Answers@Package@@QEAAJPEAPEAG@Z; Package::get_Answers(ushort * *)
0x1400558ec  mov     ebx, eax
0x1400558ee  test    eax, eax
0x1400558f0  js      loc_1400559B8
0x1400558f6  mov     rdi, [rsp+68h+bstrString]
0x1400558fb  test    rdi, rdi
0x1400558fe  jz      short loc_140055948
0x140055900  mov     r8, r12; struct IXMLDOMNode *
0x140055903  lea     rcx, [rsp+68h+arg_18]; unsigned __int16 **
0x14005590b  mov     rdx, rdi; unsigned __int16 *
0x14005590e  call    ?MetSubstituteXmlParameters@@YAJPEAPEAGPEBGPEAUIXMLDOMNode@@@Z; MetSubstituteXmlParameters(ushort * *,ushort const *,IXMLDOMNode *)
0x140055913  mov     ebx, eax
0x140055915  test    eax, eax
0x140055917  js      short loc_14005598C
0x140055919  mov     rbp, [rsp+68h+arg_18]
0x140055921  mov     rcx, r15; this
0x140055924  mov     rdx, rbp; unsigned __int16 *
0x140055927  call    ?set_Answers@Package@@QEAAJPEBG@Z; Package::set_Answers(ushort const *)
0x14005592c  mov     ebx, eax
0x14005592e  test    eax, eax
0x140055930  js      short loc_140055984
0x140055932  mov     rcx, rdi; bstrString
0x140055935  call    cs:__imp_SysFreeString
0x14005593c  nop     dword ptr [rax+rax+00h]
0x140055941  xor     edi, edi
0x140055943  mov     [rsp+68h+bstrString], rdi
0x140055948  test    rbp, rbp
0x14005594b  jz      short loc_140055977
0x14005594d  call    cs:__imp_GetProcessHeap
0x140055954  nop     dword ptr [rax+rax+00h]
0x140055959  mov     r8, rbp; lpMem
0x14005595c  xor     edx, edx; dwFlags
0x14005595e  mov     rcx, rax; hHeap
0x140055961  call    cs:__imp_HeapFree
0x140055968  nop     dword ptr [rax+rax+00h]
0x14005596d  xor     ebp, ebp
0x14005596f  mov     [rsp+68h+arg_18], rbp
0x140055977  mov     rdx, [rsp+68h+arg_8]
0x14005597c  inc     r14d
0x14005597f  jmp     loc_1400558AF
0x140055984  mov     r9d, 7B6h
0x14005598a  jmp     short loc_1400559E7
0x14005598c  mov     r9d, 7B3h
0x140055992  mov     [rsp+68h+var_48], eax
0x140055996  lea     r8, aPackagecollect_11; "PackageCollection::UpdateAnswers"
0x14005599d  mov     ecx, 1; Level
0x1400559a2  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x1400559a9  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400559ae  mov     rbp, [rsp+68h+arg_18]
0x1400559b6  jmp     short loc_140055A03
0x1400559b8  mov     r9d, 7ACh
0x1400559be  mov     [rsp+68h+var_48], eax
0x1400559c2  lea     r8, aPackagecollect_11; "PackageCollection::UpdateAnswers"
0x1400559c9  mov     ecx, 1; Level
0x1400559ce  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x1400559d5  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400559da  mov     rdi, [rsp+68h+bstrString]
0x1400559df  jmp     short loc_140055A03
0x1400559e1  mov     r9d, 7A9h
0x1400559e7  lea     r8, aPackagecollect_11; "PackageCollection::UpdateAnswers"
0x1400559ee  mov     [rsp+68h+var_48], eax
0x1400559f2  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x1400559f9  mov     ecx, 1; Level
0x1400559fe  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140055a03  test    rdi, rdi
0x140055a06  jz      short loc_140055A17
0x140055a08  mov     rcx, rdi; bstrString
0x140055a0b  call    cs:__imp_SysFreeString
0x140055a12  nop     dword ptr [rax+rax+00h]
0x140055a17  test    rbp, rbp
0x140055a1a  jz      short loc_140055A3C
0x140055a1c  call    cs:__imp_GetProcessHeap
0x140055a23  nop     dword ptr [rax+rax+00h]
0x140055a28  mov     r8, rbp; lpMem
0x140055a2b  xor     edx, edx; dwFlags
0x140055a2d  mov     rcx, rax; hHeap
0x140055a30  call    cs:__imp_HeapFree
0x140055a37  nop     dword ptr [rax+rax+00h]
0x140055a3c  lea     r11, [rsp+68h+var_28]
0x140055a41  mov     eax, ebx
0x140055a43  mov     rbx, [r11+30h]
0x140055a47  mov     rbp, [r11+40h]
0x140055a4b  mov     rsp, r11
0x140055a4e  pop     r15
0x140055a50  pop     r14
0x140055a52  pop     r13
0x140055a54  pop     r12
0x140055a56  pop     rdi
0x140055a57  retn
```
