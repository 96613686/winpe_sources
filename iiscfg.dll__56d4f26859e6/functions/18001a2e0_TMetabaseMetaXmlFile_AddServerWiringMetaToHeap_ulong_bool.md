# TMetabaseMetaXmlFile::AddServerWiringMetaToHeap(ulong,bool)

- ea: `0x18001a2e0`
- end: `0x18001a43c`
- name: `?AddServerWiringMetaToHeap@TMetabaseMetaXmlFile@@AEAAXK_N@Z`
- size: `348`
- prototype: `void __fastcall(TMetabaseMetaXmlFile *__hidden this, unsigned int, bool)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001aac4`
- `0x18001b354`

## callees

- `0x180017ad8`
- `0x18001a2e0`
- `0x18002e110`
- `0x180030010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001a397`
- `msvcrt!_wcsicmp` at `0x18001a3b9`
- `msvcrt!_wcsicmp` at `0x18001a397`
- `msvcrt!_wcsicmp` at `0x18001a3b9`

## string_xrefs

- `0x18001a380`: `inetsrv\iis\mb\config\src\core\schemagen\tmetabasemetaxmlfile.cpp`
- `0x18001a373`: `ERROR PARSING XML FILE`

## pseudocode

```c
void __fastcall TMetabaseMetaXmlFile::AddServerWiringMetaToHeap(TMetabaseMetaXmlFile *this, unsigned int a2, char a3)
{
  __int64 v4; // rax
  __int64 v7; // rax
  int v8; // eax
  const wchar_t *v9; // rax
  const wchar_t *v10; // rbx
  __int64 v11; // rdx
  __int64 (__fastcall *v12)(TMetabaseMetaXmlFile *, __int64); // rax
  int v13; // eax
  bool v14; // zf
  __int64 v15; // rax
  void (__fastcall *v16)(TMetabaseMetaXmlFile *, _OWORD *, __int64); // rax
  _OWORD v17[3]; // [rsp+20h] [rbp-40h] BYREF
  int v18; // [rsp+50h] [rbp-10h]

  v18 = 0;
  v4 = *(_QWORD *)this;
  memset(v17, 0, sizeof(v17));
  LODWORD(v17[0]) = a2;
  *(_QWORD *)((char *)v17 + 4) = (*(unsigned int (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(v4 + 16))(this, 0);
  v7 = *(_QWORD *)this;
  LODWORD(v17[1]) = 0;
  HIDWORD(v17[2]) = 0;
  if ( a3 )
  {
    v8 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, __int64))(v7 + 16))(this, 2);
  }
  else
  {
    v9 = (const wchar_t *)(*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(v7 + 144))(this, a2);
    v10 = v9;
    if ( !v9 )
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetabasemetaxmlfile.cpp",
        L"ERROR PARSING XML FILE",
        0x440u,
        0);
    if ( _wcsicmp(L"MBPropertyDiff", v9) )
    {
      v13 = _wcsicmp(L"MBProperty", v10);
      v11 = 14;
      v14 = v13 == 0;
      v12 = *(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, __int64))(*(_QWORD *)this + 16LL);
      if ( !v14 )
        v11 = 4;
    }
    else
    {
      v11 = 15;
      v12 = *(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, __int64))(*(_QWORD *)this + 16LL);
    }
    v8 = v12(this, v11);
  }
  DWORD2(v17[1]) = v8;
  v15 = *(_QWORD *)this;
  HIDWORD(v17[0]) = 0;
  DWORD1(v17[1]) = 0;
  *(_QWORD *)((char *)&v17[1] + 12) = 0;
  v16 = *(void (__fastcall **)(TMetabaseMetaXmlFile *, _OWORD *, __int64))(v15 + 104);
  v18 = 0;
  *(_QWORD *)((char *)&v17[2] + 4) = 0;
  v16(this, v17, 1);
}

```

## disassembly

```asm
0x18001a2e0  mov     [rsp-18h+arg_10], rbx
0x18001a2e5  push    rbp
0x18001a2e6  push    rsi
0x18001a2e7  push    rdi
0x18001a2e8  mov     rbp, rsp
0x18001a2eb  sub     rsp, 60h
0x18001a2ef  mov     rax, cs:__security_cookie
0x18001a2f6  xor     rax, rsp
0x18001a2f9  mov     [rbp+var_8], rax
0x18001a2fd  xor     eax, eax
0x18001a2ff  xorps   xmm0, xmm0
0x18001a302  mov     [rbp+var_10], eax
0x18001a305  mov     esi, edx
0x18001a307  mov     rax, [rcx]
0x18001a30a  mov     bl, r8b
0x18001a30d  movups  [rbp+var_40], xmm0
0x18001a311  mov     dword ptr [rbp+var_40], edx
0x18001a314  mov     rdi, rcx
0x18001a317  xor     edx, edx
0x18001a319  mov     rax, [rax+10h]
0x18001a31d  movups  [rbp+var_30], xmm0
0x18001a321  movups  [rbp+var_20], xmm0
0x18001a325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a32a  mov     dword ptr [rbp+var_40+4], eax
0x18001a32d  mov     rcx, rdi
0x18001a330  mov     rax, [rdi]
0x18001a333  mov     dword ptr [rbp+var_40+8], 0
0x18001a33a  mov     dword ptr [rbp+var_30], 0
0x18001a341  mov     dword ptr [rbp+var_20+0Ch], 0
0x18001a348  test    bl, bl
0x18001a34a  jz      short loc_18001A35A
0x18001a34c  mov     rax, [rax+10h]
0x18001a350  mov     edx, 2
0x18001a355  jmp     loc_18001A3DA
0x18001a35a  mov     rax, [rax+90h]
0x18001a361  mov     edx, esi
0x18001a363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a368  mov     rbx, rax
0x18001a36b  test    rax, rax
0x18001a36e  jnz     short loc_18001A38D
0x18001a370  xor     r9d, r9d; unsigned int
0x18001a373  lea     rdx, aErrorParsingXm; "ERROR PARSING XML FILE"
0x18001a37a  mov     r8d, 440h; unsigned int
0x18001a380  lea     rcx, aInetsrvIisMbCo_3; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001a387  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001a38d  mov     rdx, rbx; String2
0x18001a390  lea     rcx, aMbpropertydiff; "MBPropertyDiff"
0x18001a397  call    cs:__imp__wcsicmp
0x18001a39d  test    eax, eax
0x18001a39f  jnz     short loc_18001A3AF
0x18001a3a1  mov     rax, [rdi]
0x18001a3a4  mov     edx, 0Fh
0x18001a3a9  mov     rax, [rax+10h]
0x18001a3ad  jmp     short loc_18001A3D7
0x18001a3af  mov     rdx, rbx; String2
0x18001a3b2  lea     rcx, aMbproperty; "MBProperty"
0x18001a3b9  call    cs:__imp__wcsicmp
0x18001a3bf  mov     rcx, [rdi]
0x18001a3c2  mov     edx, 0Eh
0x18001a3c7  test    eax, eax
0x18001a3c9  mov     r8, [rcx+10h]
0x18001a3cd  mov     rax, r8
0x18001a3d0  jz      short loc_18001A3D7
0x18001a3d2  mov     edx, 4
0x18001a3d7  mov     rcx, rdi
0x18001a3da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3df  mov     dword ptr [rbp+var_30+8], eax
0x18001a3e2  lea     rdx, [rbp+var_40]
0x18001a3e6  mov     rax, [rdi]
0x18001a3e9  mov     r8d, 1
0x18001a3ef  mov     rcx, rdi
0x18001a3f2  mov     dword ptr [rbp+var_40+0Ch], 0
0x18001a3f9  mov     dword ptr [rbp+var_30+4], 0
0x18001a400  mov     qword ptr [rbp+var_30+0Ch], 0
0x18001a408  mov     rax, [rax+68h]
0x18001a40c  mov     [rbp+var_10], 0
0x18001a413  mov     qword ptr [rbp+var_20+4], 0
0x18001a41b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a420  mov     rcx, [rbp+var_8]
0x18001a424  xor     rcx, rsp; StackCookie
0x18001a427  call    __security_check_cookie
0x18001a42c  mov     rbx, [rsp+60h+arg_10]
0x18001a434  add     rsp, 60h
0x18001a438  pop     rdi
0x18001a439  pop     rsi
0x18001a43a  pop     rbp
0x18001a43b  retn
```
