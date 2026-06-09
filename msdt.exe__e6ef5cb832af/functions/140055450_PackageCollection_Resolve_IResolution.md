# PackageCollection::Resolve(IResolution *)

- ea: `0x140055450`
- end: `0x1400556ad`
- name: `?Resolve@PackageCollection@@UEAAJPEAVIResolution@@@Z`
- size: `605`
- prototype: `__int64 __fastcall(PackageCollection *__hidden this, struct IResolution *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x140020420`
- `0x140055450`
- `0x140063010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140055567`
- `KERNEL32!GetLastError` at `0x1400555a5`
- `KERNEL32!GetLastError` at `0x140055567`
- `KERNEL32!GetLastError` at `0x1400555a5`
- `KERNEL32!SetDllDirectoryW` at `0x140055557`
- `KERNEL32!SetDllDirectoryW` at `0x140055595`
- `KERNEL32!SetDllDirectoryW` at `0x140055557`
- `KERNEL32!SetDllDirectoryW` at `0x140055595`
- `OLEAUT32!__imp_SysFreeString` at `0x14005565d`
- `OLEAUT32!__imp_SysFreeString` at `0x14005567a`
- `OLEAUT32!__imp_SysFreeString` at `0x14005565d`
- `OLEAUT32!__imp_SysFreeString` at `0x14005567a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PackageCollection::Resolve(PackageCollection *this, struct IResolution *a2)
{
  signed int v4; // ebx
  int v5; // r9d
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  signed int LastError; // eax
  signed int v11; // eax
  int v12; // ecx
  int v14; // [rsp+20h] [rbp-20h]
  LPCWSTR lpPathName[2]; // [rsp+30h] [rbp-10h] BYREF
  __int64 v16; // [rsp+68h] [rbp+28h] BYREF
  __int64 v17; // [rsp+70h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp+38h] BYREF

  lpPathName[0] = 0;
  bstrString = 0;
  v16 = 0;
  v17 = 0;
  if ( a2 )
  {
    v6 = (*(__int64 (__fastcall **)(struct IResolution *, __int64 *))(*(_QWORD *)a2 + 128LL))(a2, &v16);
    v4 = v6;
    if ( v6 < 0 )
    {
      v14 = v6;
      v5 = 654;
      goto LABEL_4;
    }
    v7 = (*(__int64 (__fastcall **)(struct IResolution *, BSTR *))(*(_QWORD *)a2 + 48LL))(a2, &bstrString);
    v4 = v7;
    if ( v7 < 0 )
    {
      v14 = v7;
      v5 = 657;
      goto LABEL_4;
    }
    v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 96LL))(v16, &v17);
    v4 = v8;
    if ( v8 < 0 )
    {
      v14 = v8;
      v5 = 660;
      goto LABEL_4;
    }
    v9 = (*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v16 + 80LL))(v16, lpPathName);
    v4 = v9;
    if ( v9 < 0 )
    {
      v14 = v9;
      v5 = 663;
      goto LABEL_4;
    }
    if ( SetDllDirectoryW(0) )
      goto LABEL_22;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
    {
LABEL_22:
      if ( SetDllDirectoryW(lpPathName[0]) )
        goto LABEL_24;
      v11 = GetLastError();
      v4 = v11;
      if ( v11 > 0 )
        v4 = (unsigned __int16)v11 | 0x80070000;
      if ( v4 >= 0 )
      {
LABEL_24:
        if ( !*((_DWORD *)this + 16) )
        {
          v4 = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v17 + 152LL))(v17, bstrString);
          v12 = 1;
          if ( (unsigned int)(v4 + 2143551231) > 1 )
          {
            if ( v4 < 0 )
            {
              SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::Resolve", 685, v4);
              goto LABEL_29;
            }
          }
          else
          {
            v12 = 2;
          }
          *((_DWORD *)a2 + 22) = v12;
          v4 = 0;
          goto LABEL_29;
        }
        v4 = -2147467260;
        v5 = 673;
      }
      else
      {
        v5 = 669;
      }
    }
    else
    {
      v5 = 666;
    }
  }
  else
  {
    v4 = -2147024809;
    v5 = 651;
  }
  v14 = v4;
LABEL_4:
  SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::Resolve", v5, v14);
LABEL_29:
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( lpPathName[0] )
    SysFreeString((BSTR)lpPathName[0]);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140055450  mov     [rsp-18h+arg_0], rbx
0x140055455  push    rbp
0x140055456  push    rsi
0x140055457  push    rdi
0x140055458  mov     rbp, rsp
0x14005545b  sub     rsp, 40h
0x14005545f  mov     [rbp+lpPathName], 0
0x140055467  mov     rdi, rdx
0x14005546a  mov     [rbp+bstrString], 0
0x140055472  mov     rsi, rcx
0x140055475  mov     [rbp+arg_8], 0
0x14005547d  mov     [rbp+arg_10], 0
0x140055485  test    rdx, rdx
0x140055488  jnz     short loc_1400554B6
0x14005548a  mov     ebx, 80070057h
0x14005548f  mov     r9d, 28Bh
0x140055495  mov     [rsp+40h+var_20], ebx
0x140055499  mov     ecx, 1; Level
0x14005549e  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x1400554a5  lea     r8, aPackagecollect_26; "PackageCollection::Resolve"
0x1400554ac  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400554b1  jmp     loc_14005561A
0x1400554b6  mov     rax, [rdx]
0x1400554b9  mov     rcx, rdi
0x1400554bc  lea     rdx, [rbp+arg_8]
0x1400554c0  mov     rax, [rax+80h]
0x1400554c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400554cc  mov     ebx, eax
0x1400554ce  test    eax, eax
0x1400554d0  jns     short loc_1400554DE
0x1400554d2  mov     [rsp+40h+var_20], eax
0x1400554d6  mov     r9d, 28Eh
0x1400554dc  jmp     short loc_140055499
0x1400554de  mov     rax, [rdi]
0x1400554e1  lea     rdx, [rbp+bstrString]
0x1400554e5  mov     rcx, rdi
0x1400554e8  mov     rax, [rax+30h]
0x1400554ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400554f1  mov     ebx, eax
0x1400554f3  test    eax, eax
0x1400554f5  jns     short loc_140055503
0x1400554f7  mov     [rsp+40h+var_20], eax
0x1400554fb  mov     r9d, 291h
0x140055501  jmp     short loc_140055499
0x140055503  mov     rcx, [rbp+arg_8]
0x140055507  lea     rdx, [rbp+arg_10]
0x14005550b  mov     rax, [rcx]
0x14005550e  mov     rax, [rax+60h]
0x140055512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055517  mov     ebx, eax
0x140055519  test    eax, eax
0x14005551b  jns     short loc_14005552C
0x14005551d  mov     [rsp+40h+var_20], eax
0x140055521  mov     r9d, 294h
0x140055527  jmp     loc_140055499
0x14005552c  mov     rcx, [rbp+arg_8]
0x140055530  lea     rdx, [rbp+lpPathName]
0x140055534  mov     rax, [rcx]
0x140055537  mov     rax, [rax+50h]
0x14005553b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055540  mov     ebx, eax
0x140055542  test    eax, eax
0x140055544  jns     short loc_140055555
0x140055546  mov     [rsp+40h+var_20], eax
0x14005554a  mov     r9d, 297h
0x140055550  jmp     loc_140055499
0x140055555  xor     ecx, ecx; lpPathName
0x140055557  call    cs:__imp_SetDllDirectoryW
0x14005555e  nop     dword ptr [rax+rax+00h]
0x140055563  test    eax, eax
0x140055565  jnz     short loc_140055591
0x140055567  call    cs:__imp_GetLastError
0x14005556e  nop     dword ptr [rax+rax+00h]
0x140055573  mov     ebx, eax
0x140055575  test    eax, eax
0x140055577  jle     short loc_140055582
0x140055579  movzx   ebx, ax
0x14005557c  or      ebx, 80070000h
0x140055582  test    ebx, ebx
0x140055584  jns     short loc_140055591
0x140055586  mov     r9d, 29Ah
0x14005558c  jmp     loc_140055495
0x140055591  mov     rcx, [rbp+lpPathName]; lpPathName
0x140055595  call    cs:__imp_SetDllDirectoryW
0x14005559c  nop     dword ptr [rax+rax+00h]
0x1400555a1  test    eax, eax
0x1400555a3  jnz     short loc_1400555CF
0x1400555a5  call    cs:__imp_GetLastError
0x1400555ac  nop     dword ptr [rax+rax+00h]
0x1400555b1  mov     ebx, eax
0x1400555b3  test    eax, eax
0x1400555b5  jle     short loc_1400555C0
0x1400555b7  movzx   ebx, ax
0x1400555ba  or      ebx, 80070000h
0x1400555c0  test    ebx, ebx
0x1400555c2  jns     short loc_1400555CF
0x1400555c4  mov     r9d, 29Dh
0x1400555ca  jmp     loc_140055495
0x1400555cf  cmp     dword ptr [rsi+40h], 0
0x1400555d3  jz      short loc_1400555E5
0x1400555d5  mov     ebx, 80004004h
0x1400555da  mov     r9d, 2A1h
0x1400555e0  jmp     loc_140055495
0x1400555e5  mov     rcx, [rbp+arg_10]
0x1400555e9  mov     rdx, [rbp+bstrString]
0x1400555ed  mov     rax, [rcx]
0x1400555f0  mov     rax, [rax+98h]
0x1400555f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400555fc  mov     ebx, eax
0x1400555fe  mov     ecx, 1
0x140055603  add     eax, 7FC3FEFFh
0x140055608  cmp     eax, ecx
0x14005560a  ja      loc_140055696
0x140055610  mov     ecx, 2
0x140055615  mov     [rdi+58h], ecx
0x140055618  xor     ebx, ebx
0x14005561a  mov     rcx, [rbp+arg_8]
0x14005561e  test    rcx, rcx
0x140055621  jz      short loc_140055637
0x140055623  mov     rax, [rcx]
0x140055626  mov     rax, [rax+10h]
0x14005562a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005562f  mov     [rbp+arg_8], 0
0x140055637  mov     rcx, [rbp+arg_10]
0x14005563b  test    rcx, rcx
0x14005563e  jz      short loc_140055654
0x140055640  mov     rax, [rcx]
0x140055643  mov     rax, [rax+10h]
0x140055647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005564c  mov     [rbp+arg_10], 0
0x140055654  mov     rcx, [rbp+bstrString]; bstrString
0x140055658  test    rcx, rcx
0x14005565b  jz      short loc_140055671
0x14005565d  call    cs:__imp_SysFreeString
0x140055664  nop     dword ptr [rax+rax+00h]
0x140055669  mov     [rbp+bstrString], 0
0x140055671  mov     rcx, [rbp+lpPathName]; bstrString
0x140055675  test    rcx, rcx
0x140055678  jz      short loc_140055686
0x14005567a  call    cs:__imp_SysFreeString
0x140055681  nop     dword ptr [rax+rax+00h]
0x140055686  mov     eax, ebx
0x140055688  mov     rbx, [rsp+40h+arg_0]
0x14005568d  add     rsp, 40h
0x140055691  pop     rdi
0x140055692  pop     rsi
0x140055693  pop     rbp
0x140055694  retn
0x140055696  test    ebx, ebx
0x140055698  jns     loc_140055615
0x14005569e  mov     [rsp+40h+var_20], ebx
0x1400556a2  mov     r9d, 2ADh
0x1400556a8  jmp     loc_14005549E
```
