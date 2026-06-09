# CFatVolume::_Initialize(ushort *)

- ea: `0x18003e238`
- end: `0x18003e3a8`
- name: `?_Initialize@CFatVolume@@AEAAJPEAG@Z`
- size: `368`
- prototype: `__int64 __fastcall(CFatVolume *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180037b70`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x1800157fc`
- `0x18001913c`
- `0x18001a630`
- `0x18003e238`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003e314`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003e314`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e32b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e32b`

## pseudocode

```c
__int64 __fastcall CFatVolume::_Initialize(CFatVolume *this, unsigned __int16 *a2)
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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v16, "CFatVolume::_Initialize", 811, 1);
  v4 = 813;
  if ( a2 )
  {
    v16 = 0;
    v17 = 813;
    *((_DWORD *)this + 96) = 0;
    v6 = (LPCWSTR *)((char *)this + 48);
    LastFailureAsHRESULT = CBsString::Set((CFatVolume *)((char *)this + 48), a2);
    v16 = LastFailureAsHRESULT;
    v4 = 818;
    if ( LastFailureAsHRESULT >= 0 )
    {
      v17 = 818;
      LastFailureAsHRESULT = CBsString::Trailing((CFatVolume *)((char *)this + 48), v7);
      v16 = LastFailureAsHRESULT;
      v4 = 819;
      if ( LastFailureAsHRESULT >= 0 )
      {
        v17 = 819;
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
          v17 = 831;
          LastFailureAsHRESULT = (*(__int64 (__fastcall **)(CFatVolume *, char *))(*(_QWORD *)this + 48LL))(
                                   this,
                                   (char *)this + 408);
          v16 = LastFailureAsHRESULT;
          v4 = 834;
          if ( LastFailureAsHRESULT >= 0 )
          {
            v17 = 834;
            goto LABEL_14;
          }
        }
        else
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v14, v10, v12, v13);
          v16 = LastFailureAsHRESULT;
          v4 = 831;
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
LABEL_14:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18003e238  push    rbp
0x18003e23a  push    rbx
0x18003e23b  push    rsi
0x18003e23c  push    rdi
0x18003e23d  lea     rbp, [rsp-3Fh]
0x18003e242  sub     rsp, 88h
0x18003e249  mov     rbx, rdx
0x18003e24c  mov     rdi, rcx
0x18003e24f  mov     r9d, 1; unsigned __int16
0x18003e255  mov     r8d, 32Bh; unsigned __int16
0x18003e25b  lea     rdx, aCfatvolumeInit; "CFatVolume::_Initialize"
0x18003e262  lea     rcx, [rbp+57h+var_60]; this
0x18003e266  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18003e26b  nop
0x18003e26c  mov     eax, 32Dh
0x18003e271  test    rbx, rbx
0x18003e274  jnz     short loc_18003E287
0x18003e276  mov     ebx, 80070057h
0x18003e27b  mov     [rbp+57h+var_60], ebx
0x18003e27e  mov     [rbp+57h+var_5A], ax
0x18003e282  jmp     loc_18003E391
0x18003e287  mov     [rbp+57h+var_60], 0
0x18003e28e  mov     [rbp+57h+var_5C], ax
0x18003e292  mov     dword ptr [rdi+180h], 0
0x18003e29c  lea     rsi, [rdi+30h]
0x18003e2a0  mov     rdx, rbx; unsigned __int16 *
0x18003e2a3  mov     rcx, rsi; this
0x18003e2a6  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18003e2ab  mov     ebx, eax
0x18003e2ad  mov     [rbp+57h+var_60], eax
0x18003e2b0  test    eax, eax
0x18003e2b2  mov     eax, 332h
0x18003e2b7  js      short loc_18003E27E
0x18003e2b9  mov     [rbp+57h+var_5C], ax
0x18003e2bd  mov     rcx, rsi; this
0x18003e2c0  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x18003e2c5  mov     ebx, eax
0x18003e2c7  mov     [rbp+57h+var_60], eax
0x18003e2ca  test    eax, eax
0x18003e2cc  mov     eax, 333h
0x18003e2d1  js      short loc_18003E27E
0x18003e2d3  mov     [rbp+57h+var_5C], ax
0x18003e2d7  mov     eax, [rdi+38h]
0x18003e2da  lea     ecx, [rax-1]
0x18003e2dd  cmp     ecx, eax
0x18003e2df  jnb     short loc_18003E2ED
0x18003e2e1  mov     [rsi+8], ecx
0x18003e2e4  mov     rdx, [rsi]
0x18003e2e7  xor     eax, eax
0x18003e2e9  mov     [rdx+rcx*2], ax
0x18003e2ed  mov     [rsp+0A0h+hTemplateFile], 0; hTemplateFile
0x18003e2f6  mov     [rsp+0A0h+dwFlagsAndAttributes], 20000080h; dwFlagsAndAttributes
0x18003e2fe  mov     r8d, 3; dwShareMode
0x18003e304  mov     [rsp+0A0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18003e309  xor     r9d, r9d; lpSecurityAttributes
0x18003e30c  mov     edx, 0C0000000h; dwDesiredAccess
0x18003e311  mov     rcx, [rsi]; lpFileName
0x18003e314  call    cs:__imp_CreateFileW
0x18003e31a  mov     rbx, rax
0x18003e31d  mov     rcx, [rdi+28h]; hObject
0x18003e321  lea     rax, [rcx-1]
0x18003e325  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003e329  ja      short loc_18003E331
0x18003e32b  call    cs:__imp_CloseHandle
0x18003e331  mov     [rdi+28h], rbx
0x18003e335  lea     rax, [rbx+1]
0x18003e339  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003e33f  jnz     short loc_18003E355
0x18003e341  call    GetLastFailureAsHRESULT
0x18003e346  mov     ebx, eax
0x18003e348  mov     [rbp+57h+var_60], eax
0x18003e34b  mov     eax, 33Fh
0x18003e350  jmp     loc_18003E27E
0x18003e355  mov     [rbp+57h+var_60], 0
0x18003e35c  mov     eax, 33Fh
0x18003e361  mov     [rbp+57h+var_5C], ax
0x18003e365  mov     rax, [rdi]
0x18003e368  lea     rdx, [rdi+198h]
0x18003e36f  mov     rcx, rdi
0x18003e372  mov     rax, [rax+30h]
0x18003e376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e37b  mov     ebx, eax
0x18003e37d  mov     [rbp+57h+var_60], eax
0x18003e380  test    eax, eax
0x18003e382  mov     eax, 342h
0x18003e387  js      loc_18003E27E
0x18003e38d  mov     [rbp+57h+var_5C], ax
0x18003e391  lea     rcx, [rbp+57h+var_60]; this
0x18003e395  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18003e39a  mov     eax, ebx
0x18003e39c  add     rsp, 88h
0x18003e3a3  pop     rdi
0x18003e3a4  pop     rsi
0x18003e3a5  pop     rbx
0x18003e3a6  pop     rbp
0x18003e3a7  retn
```
