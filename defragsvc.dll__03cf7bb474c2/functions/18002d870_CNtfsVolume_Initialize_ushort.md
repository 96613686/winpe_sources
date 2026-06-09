# CNtfsVolume::_Initialize(ushort *)

- ea: `0x18002d870`
- end: `0x18002d9a0`
- name: `?_Initialize@CNtfsVolume@@EEAAJPEAG@Z`
- size: `304`
- prototype: `__int64 __fastcall(CNtfsVolume *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001913c`
- `0x18001a630`
- `0x18002d870`
- `0x18006495c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d91a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d91a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d931`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d931`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CNtfsVolume::_Initialize(CNtfsVolume *this, unsigned __int16 *a2)
{
  __int16 v4; // ax
  int LastFailureAsHRESULT; // ebx
  __int64 v6; // rdx
  HANDLE FileW; // rbx
  __int64 v8; // r8
  __int64 v9; // r9
  char *v10; // rcx
  int v12; // [rsp+40h] [rbp-9h] BYREF
  __int16 v13; // [rsp+44h] [rbp-5h]
  __int16 v14; // [rsp+46h] [rbp-3h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v12, "CNtfsVolume::_Initialize", 1211, 1);
  v4 = 1213;
  if ( a2 )
  {
    v12 = 0;
    v13 = 1213;
    *((_DWORD *)this + 96) = 0;
    LastFailureAsHRESULT = CBsString::Set((CNtfsVolume *)((char *)this + 48), a2);
    v12 = LastFailureAsHRESULT;
    v4 = 1218;
    if ( LastFailureAsHRESULT >= 0 )
    {
      v13 = 1218;
      FileW = CreateFileW(*((LPCWSTR *)this + 6), 0xC0000000, 3u, 0, 3u, 0x20000080u, 0);
      v10 = (char *)*((_QWORD *)this + 5);
      if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v10);
      *((_QWORD *)this + 5) = FileW;
      if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      {
        v12 = 0;
        v13 = 1229;
        LastFailureAsHRESULT = CVolume::_DiscoverTiers(this);
        v12 = LastFailureAsHRESULT;
        v4 = 1231;
        if ( LastFailureAsHRESULT >= 0 )
        {
          v13 = 1231;
          goto LABEL_11;
        }
      }
      else
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v10, v6, v8, v9);
        v12 = LastFailureAsHRESULT;
        v4 = 1229;
      }
    }
  }
  else
  {
    LastFailureAsHRESULT = -2147024809;
    v12 = -2147024809;
  }
  v14 = v4;
LABEL_11:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v12);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18002d870  push    rbp
0x18002d872  push    rbx
0x18002d873  push    rsi
0x18002d874  push    rdi
0x18002d875  lea     rbp, [rsp-3Fh]
0x18002d87a  sub     rsp, 88h
0x18002d881  mov     rbx, rdx
0x18002d884  mov     rdi, rcx
0x18002d887  mov     r9d, 1; unsigned __int16
0x18002d88d  mov     r8d, 4BBh; unsigned __int16
0x18002d893  lea     rdx, aCntfsvolumeIni; "CNtfsVolume::_Initialize"
0x18002d89a  lea     rcx, [rbp+57h+var_60]; this
0x18002d89e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002d8a3  nop
0x18002d8a4  mov     eax, 4BDh
0x18002d8a9  test    rbx, rbx
0x18002d8ac  jnz     short loc_18002D8BF
0x18002d8ae  mov     ebx, 80070057h
0x18002d8b3  mov     [rbp+57h+var_60], ebx
0x18002d8b6  mov     [rbp+57h+var_5A], ax
0x18002d8ba  jmp     loc_18002D989
0x18002d8bf  mov     [rbp+57h+var_60], 0
0x18002d8c6  mov     [rbp+57h+var_5C], ax
0x18002d8ca  mov     dword ptr [rdi+180h], 0
0x18002d8d4  mov     rdx, rbx; unsigned __int16 *
0x18002d8d7  lea     rcx, [rdi+30h]; this
0x18002d8db  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18002d8e0  mov     ebx, eax
0x18002d8e2  mov     [rbp+57h+var_60], eax
0x18002d8e5  test    eax, eax
0x18002d8e7  mov     eax, 4C2h
0x18002d8ec  js      short loc_18002D8B6
0x18002d8ee  mov     [rbp+57h+var_5C], ax
0x18002d8f2  mov     [rsp+0A0h+hTemplateFile], 0; hTemplateFile
0x18002d8fb  mov     [rsp+0A0h+dwFlagsAndAttributes], 20000080h; dwFlagsAndAttributes
0x18002d903  mov     r8d, 3; dwShareMode
0x18002d909  mov     [rsp+0A0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18002d90e  xor     r9d, r9d; lpSecurityAttributes
0x18002d911  mov     edx, 0C0000000h; dwDesiredAccess
0x18002d916  mov     rcx, [rdi+30h]; lpFileName
0x18002d91a  call    cs:__imp_CreateFileW
0x18002d920  mov     rbx, rax
0x18002d923  mov     rcx, [rdi+28h]; hObject
0x18002d927  lea     rax, [rcx-1]
0x18002d92b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002d92f  ja      short loc_18002D937
0x18002d931  call    cs:__imp_CloseHandle
0x18002d937  mov     [rdi+28h], rbx
0x18002d93b  lea     rax, [rbx+1]
0x18002d93f  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002d945  jnz     short loc_18002D95B
0x18002d947  call    GetLastFailureAsHRESULT
0x18002d94c  mov     ebx, eax
0x18002d94e  mov     [rbp+57h+var_60], eax
0x18002d951  mov     eax, 4CDh
0x18002d956  jmp     loc_18002D8B6
0x18002d95b  mov     [rbp+57h+var_60], 0
0x18002d962  mov     eax, 4CDh
0x18002d967  mov     [rbp+57h+var_5C], ax
0x18002d96b  mov     rcx, rdi; this
0x18002d96e  call    ?_DiscoverTiers@CVolume@@IEAAJXZ; CVolume::_DiscoverTiers(void)
0x18002d973  mov     ebx, eax
0x18002d975  mov     [rbp+57h+var_60], eax
0x18002d978  test    eax, eax
0x18002d97a  mov     eax, 4CFh
0x18002d97f  js      loc_18002D8B6
0x18002d985  mov     [rbp+57h+var_5C], ax
0x18002d989  lea     rcx, [rbp+57h+var_60]; this
0x18002d98d  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002d992  mov     eax, ebx
0x18002d994  add     rsp, 88h
0x18002d99b  pop     rdi
0x18002d99c  pop     rsi
0x18002d99d  pop     rbx
0x18002d99e  pop     rbp
0x18002d99f  retn
```
