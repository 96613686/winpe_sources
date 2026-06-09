# CReFsVolume::_Initialize(ushort *)

- ea: `0x18003d308`
- end: `0x18003d496`
- name: `?_Initialize@CReFsVolume@@AEAAJPEAG@Z`
- size: `398`
- prototype: `__int64 __fastcall(CReFsVolume *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180037db8`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x1800157fc`
- `0x18001913c`
- `0x18001a630`
- `0x18003d308`
- `0x18006495c`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003d3e4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003d3e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d3fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d3fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CReFsVolume::_Initialize(CReFsVolume *this, unsigned __int16 *a2)
{
  __int16 v4; // ax
  int LastFailureAsHRESULT; // ebx
  LPCWSTR *v6; // rsi
  unsigned __int16 v7; // dx
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rdx
  HANDLE FileW; // rbx
  __int64 v12; // r8
  __int64 v13; // r9
  char *v14; // rcx
  int v16; // [rsp+40h] [rbp-9h] BYREF
  __int16 v17; // [rsp+44h] [rbp-5h]
  __int16 v18; // [rsp+46h] [rbp-3h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v16, "CReFsVolume::_Initialize", 942, 1);
  v4 = 944;
  if ( a2 )
  {
    v16 = 0;
    v17 = 944;
    *((_DWORD *)this + 96) = 0;
    v6 = (LPCWSTR *)((char *)this + 48);
    LastFailureAsHRESULT = CBsString::Set((CReFsVolume *)((char *)this + 48), a2);
    v16 = LastFailureAsHRESULT;
    v4 = 949;
    if ( LastFailureAsHRESULT >= 0 )
    {
      v17 = 949;
      LastFailureAsHRESULT = CBsString::Trailing((CReFsVolume *)((char *)this + 48), v7);
      v16 = LastFailureAsHRESULT;
      v4 = 950;
      if ( LastFailureAsHRESULT >= 0 )
      {
        v17 = 950;
        v8 = *((_DWORD *)this + 14);
        v9 = (unsigned int)(v8 - 1);
        if ( v8 )
        {
          *((_DWORD *)this + 14) = v9;
          (*v6)[v9] = 0;
        }
        FileW = CreateFileW(*v6, 0xC0000000, 3u, 0, 3u, 0x20000080u, 0);
        v14 = (char *)*((_QWORD *)this + 5);
        if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v14);
        *((_QWORD *)this + 5) = FileW;
        if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
        {
          v16 = 0;
          v17 = 962;
          LastFailureAsHRESULT = (*(__int64 (__fastcall **)(CReFsVolume *, char *))(*(_QWORD *)this + 48LL))(
                                   this,
                                   (char *)this + 392);
          v16 = LastFailureAsHRESULT;
          v4 = 965;
          if ( LastFailureAsHRESULT >= 0 )
          {
            v17 = 965;
            LastFailureAsHRESULT = CVolume::_DiscoverTiers(this);
            v16 = LastFailureAsHRESULT;
            v4 = 967;
            if ( LastFailureAsHRESULT >= 0 )
            {
              v17 = 967;
              goto LABEL_15;
            }
          }
        }
        else
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v14, v10, v12, v13);
          v16 = LastFailureAsHRESULT;
          v4 = 962;
        }
      }
    }
  }
  else
  {
    LastFailureAsHRESULT = -2147024809;
    v16 = -2147024809;
  }
  v18 = v4;
LABEL_15:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18003d308  push    rbp
0x18003d30a  push    rbx
0x18003d30b  push    rsi
0x18003d30c  push    rdi
0x18003d30d  lea     rbp, [rsp-3Fh]
0x18003d312  sub     rsp, 88h
0x18003d319  mov     rbx, rdx
0x18003d31c  mov     rdi, rcx
0x18003d31f  mov     r9d, 1; unsigned __int16
0x18003d325  mov     r8d, 3AEh; unsigned __int16
0x18003d32b  lea     rdx, aCrefsvolumeIni; "CReFsVolume::_Initialize"
0x18003d332  lea     rcx, [rbp+57h+var_60]; this
0x18003d336  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18003d33b  nop
0x18003d33c  mov     eax, 3B0h
0x18003d341  test    rbx, rbx
0x18003d344  jnz     short loc_18003D357
0x18003d346  mov     ebx, 80070057h
0x18003d34b  mov     [rbp+57h+var_60], ebx
0x18003d34e  mov     [rbp+57h+var_5A], ax
0x18003d352  jmp     loc_18003D47F
0x18003d357  mov     [rbp+57h+var_60], 0
0x18003d35e  mov     [rbp+57h+var_5C], ax
0x18003d362  mov     dword ptr [rdi+180h], 0
0x18003d36c  lea     rsi, [rdi+30h]
0x18003d370  mov     rdx, rbx; unsigned __int16 *
0x18003d373  mov     rcx, rsi; this
0x18003d376  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18003d37b  mov     ebx, eax
0x18003d37d  mov     [rbp+57h+var_60], eax
0x18003d380  test    eax, eax
0x18003d382  mov     eax, 3B5h
0x18003d387  js      short loc_18003D34E
0x18003d389  mov     [rbp+57h+var_5C], ax
0x18003d38d  mov     rcx, rsi; this
0x18003d390  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x18003d395  mov     ebx, eax
0x18003d397  mov     [rbp+57h+var_60], eax
0x18003d39a  test    eax, eax
0x18003d39c  mov     eax, 3B6h
0x18003d3a1  js      short loc_18003D34E
0x18003d3a3  mov     [rbp+57h+var_5C], ax
0x18003d3a7  mov     eax, [rdi+38h]
0x18003d3aa  lea     ecx, [rax-1]
0x18003d3ad  cmp     ecx, eax
0x18003d3af  jnb     short loc_18003D3BD
0x18003d3b1  mov     [rsi+8], ecx
0x18003d3b4  mov     rdx, [rsi]
0x18003d3b7  xor     eax, eax
0x18003d3b9  mov     [rdx+rcx*2], ax
0x18003d3bd  mov     [rsp+0A0h+hTemplateFile], 0; hTemplateFile
0x18003d3c6  mov     [rsp+0A0h+dwFlagsAndAttributes], 20000080h; dwFlagsAndAttributes
0x18003d3ce  mov     r8d, 3; dwShareMode
0x18003d3d4  mov     [rsp+0A0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18003d3d9  xor     r9d, r9d; lpSecurityAttributes
0x18003d3dc  mov     edx, 0C0000000h; dwDesiredAccess
0x18003d3e1  mov     rcx, [rsi]; lpFileName
0x18003d3e4  call    cs:__imp_CreateFileW
0x18003d3ea  mov     rbx, rax
0x18003d3ed  mov     rcx, [rdi+28h]; hObject
0x18003d3f1  lea     rax, [rcx-1]
0x18003d3f5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003d3f9  ja      short loc_18003D401
0x18003d3fb  call    cs:__imp_CloseHandle
0x18003d401  mov     [rdi+28h], rbx
0x18003d405  lea     rax, [rbx+1]
0x18003d409  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003d40f  jnz     short loc_18003D425
0x18003d411  call    GetLastFailureAsHRESULT
0x18003d416  mov     ebx, eax
0x18003d418  mov     [rbp+57h+var_60], eax
0x18003d41b  mov     eax, 3C2h
0x18003d420  jmp     loc_18003D34E
0x18003d425  mov     [rbp+57h+var_60], 0
0x18003d42c  mov     eax, 3C2h
0x18003d431  mov     [rbp+57h+var_5C], ax
0x18003d435  mov     rax, [rdi]
0x18003d438  lea     rdx, [rdi+188h]
0x18003d43f  mov     rcx, rdi
0x18003d442  mov     rax, [rax+30h]
0x18003d446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d44b  mov     ebx, eax
0x18003d44d  mov     [rbp+57h+var_60], eax
0x18003d450  test    eax, eax
0x18003d452  mov     eax, 3C5h
0x18003d457  js      loc_18003D34E
0x18003d45d  mov     [rbp+57h+var_5C], ax
0x18003d461  mov     rcx, rdi; this
0x18003d464  call    ?_DiscoverTiers@CVolume@@IEAAJXZ; CVolume::_DiscoverTiers(void)
0x18003d469  mov     ebx, eax
0x18003d46b  mov     [rbp+57h+var_60], eax
0x18003d46e  test    eax, eax
0x18003d470  mov     eax, 3C7h
0x18003d475  js      loc_18003D34E
0x18003d47b  mov     [rbp+57h+var_5C], ax
0x18003d47f  lea     rcx, [rbp+57h+var_60]; this
0x18003d483  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18003d488  mov     eax, ebx
0x18003d48a  add     rsp, 88h
0x18003d491  pop     rdi
0x18003d492  pop     rsi
0x18003d493  pop     rbx
0x18003d494  pop     rbp
0x18003d495  retn
```
