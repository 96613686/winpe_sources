# CFreeSpaceManager::_Initialize(ushort *,unsigned __int64)

- ea: `0x18001ac88`
- end: `0x18001ada3`
- name: `?_Initialize@CFreeSpaceManager@@AEAAJPEAG_K@Z`
- size: `283`
- prototype: `__int64 __fastcall(CFreeSpaceManager *this, unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000c848`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001a630`
- `0x18001ac88`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001acff`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001acff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ad60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ad60`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFreeSpaceManager::_Initialize(CFreeSpaceManager *this, unsigned __int16 *a2, __int64 a3)
{
  __int16 v6; // ax
  HANDLE FileW; // rdi
  __int64 v8; // r8
  __int64 v9; // r9
  char *v10; // rcx
  char *v11; // rdx
  int LastFailureAsHRESULT; // ebx
  int v14; // [rsp+40h] [rbp-9h] BYREF
  __int16 v15; // [rsp+44h] [rbp-5h]
  __int16 v16; // [rsp+46h] [rbp-3h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v14, "CFreeSpaceManager::_Initialize", 662, 1);
  v6 = 664;
  if ( a2 )
  {
    v14 = 0;
    v15 = 664;
    FileW = CreateFileW(a2, 0xC0000000, 3u, 0, 3u, 0x20000080u, 0);
    v10 = (char *)*((_QWORD *)this + 24);
    v11 = v10 - 1;
    if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v10);
    *((_QWORD *)this + 24) = FileW;
    if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      v14 = 0;
      v15 = 675;
      *((_QWORD *)this + 25) = a3;
      LastFailureAsHRESULT = (*(__int64 (__fastcall **)(CFreeSpaceManager *))(*(_QWORD *)this + 24LL))(this);
      v14 = LastFailureAsHRESULT;
      v6 = 684;
      if ( LastFailureAsHRESULT >= 0 )
      {
        v15 = 684;
        goto LABEL_7;
      }
    }
    else
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v10, v11, v8, v9);
      v14 = LastFailureAsHRESULT;
      v6 = 675;
    }
  }
  else
  {
    LastFailureAsHRESULT = -2147024809;
    v14 = -2147024809;
  }
  v16 = v6;
LABEL_7:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v14);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18001ac88  push    rbp
0x18001ac8a  push    rbx
0x18001ac8b  push    rsi
0x18001ac8c  push    rdi
0x18001ac8d  lea     rbp, [rsp-3Fh]
0x18001ac92  sub     rsp, 88h
0x18001ac99  mov     rsi, r8
0x18001ac9c  mov     rdi, rdx
0x18001ac9f  mov     rbx, rcx
0x18001aca2  mov     r9d, 1; unsigned __int16
0x18001aca8  mov     r8d, 296h; unsigned __int16
0x18001acae  lea     rdx, aCfreespacemana_0; "CFreeSpaceManager::_Initialize"
0x18001acb5  lea     rcx, [rbp+57h+var_60]; this
0x18001acb9  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001acbe  nop
0x18001acbf  mov     eax, 298h
0x18001acc4  test    rdi, rdi
0x18001acc7  jz      loc_18001AD56
0x18001accd  mov     [rbp+57h+var_60], 0
0x18001acd4  mov     [rbp+57h+var_5C], ax
0x18001acd8  mov     [rsp+0A0h+hTemplateFile], 0; hTemplateFile
0x18001ace1  mov     [rsp+0A0h+dwFlagsAndAttributes], 20000080h; dwFlagsAndAttributes
0x18001ace9  mov     r8d, 3; dwShareMode
0x18001acef  mov     [rsp+0A0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18001acf4  xor     r9d, r9d; lpSecurityAttributes
0x18001acf7  mov     edx, 0C0000000h; dwDesiredAccess
0x18001acfc  mov     rcx, rdi; lpFileName
0x18001acff  call    cs:__imp_CreateFileW
0x18001ad05  mov     rdi, rax
0x18001ad08  mov     rcx, [rbx+0C0h]; hObject
0x18001ad0f  lea     rdx, [rcx-1]
0x18001ad13  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001ad17  jbe     short loc_18001AD60
0x18001ad19  mov     [rbx+0C0h], rdi
0x18001ad20  lea     rax, [rdi+1]
0x18001ad24  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001ad2a  jnz     short loc_18001AD68
0x18001ad2c  call    GetLastFailureAsHRESULT
0x18001ad31  mov     ebx, eax
0x18001ad33  mov     [rbp+57h+var_60], eax
0x18001ad36  mov     eax, 2A3h
0x18001ad3b  mov     [rbp+57h+var_5A], ax
0x18001ad3f  lea     rcx, [rbp+57h+var_60]; this
0x18001ad43  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001ad48  mov     eax, ebx
0x18001ad4a  add     rsp, 88h
0x18001ad51  pop     rdi
0x18001ad52  pop     rsi
0x18001ad53  pop     rbx
0x18001ad54  pop     rbp
0x18001ad55  retn
0x18001ad56  mov     ebx, 80070057h
0x18001ad5b  mov     [rbp+57h+var_60], ebx
0x18001ad5e  jmp     short loc_18001AD3B
0x18001ad60  call    cs:__imp_CloseHandle
0x18001ad66  jmp     short loc_18001AD19
0x18001ad68  mov     [rbp+57h+var_60], 0
0x18001ad6f  mov     eax, 2A3h
0x18001ad74  mov     [rbp+57h+var_5C], ax
0x18001ad78  mov     [rbx+0C8h], rsi
0x18001ad7f  mov     rax, [rbx]
0x18001ad82  mov     rcx, rbx
0x18001ad85  mov     rax, [rax+18h]
0x18001ad89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad8e  mov     ebx, eax
0x18001ad90  mov     [rbp+57h+var_60], eax
0x18001ad93  test    eax, eax
0x18001ad95  mov     eax, 2ACh
0x18001ad9a  js      short loc_18001AD3B
0x18001ad9c  mov     [rbp+57h+var_5C], ax
0x18001ada0  jmp     short loc_18001AD3F
```
