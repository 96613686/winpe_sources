# CFreeSlabManager::_Initialize(ushort *,unsigned __int64,ulong,unsigned __int64,unsigned __int64,CFreeSlabManagerDelegate *,IIoControl *,int)

- ea: `0x18003dad4`
- end: `0x18003dd57`
- name: `?_Initialize@CFreeSlabManager@@AEAAJPEAG_KK11PEAVCFreeSlabManagerDelegate@@PEAVIIoControl@@H@Z`
- size: `643`
- prototype: `__int64 __fastcall(CFreeSlabManager *this, unsigned __int16 *, __int64, int, unsigned __int64, unsigned __int64, struct CFreeSlabManagerDelegate *, struct IIoControl *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180038064`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001a630`
- `0x18003dad4`
- `0x18003dd60`
- `0x1800441ac`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003db74`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003db74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003db8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003db8b`

## pseudocode

```c
__int64 __fastcall CFreeSlabManager::_Initialize(
        CFreeSlabManager *this,
        unsigned __int16 *a2,
        __int64 a3,
        int a4,
        unsigned __int64 a5,
        unsigned __int64 a6,
        struct CFreeSlabManagerDelegate *a7,
        struct IIoControl *a8,
        int a9)
{
  __int16 v13; // ax
  int LastFailureAsHRESULT; // ebx
  __int64 v15; // rdx
  HANDLE FileW; // rbx
  __int64 v17; // r8
  __int64 v18; // r9
  char *v19; // rcx
  bool v20; // al
  bool v21; // r14
  CFreeSlabManagerDelegate *v22; // rcx
  CFreeSlabManagerDelegate *v23; // rax
  CFreeSlabManagerDelegate *v24; // rsi
  __int64 (__fastcall **v25)(CFreeSlabManagerDelegate *); // rax
  int v27; // [rsp+40h] [rbp-41h] BYREF
  __int16 v28; // [rsp+44h] [rbp-3Dh]
  __int16 v29; // [rsp+46h] [rbp-3Bh]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v27, "CFreeSlabManager::_Initialize", 1685, 1);
  v13 = 1688;
  if ( !a2 )
  {
    LastFailureAsHRESULT = -2147024809;
LABEL_23:
    v27 = LastFailureAsHRESULT;
    goto LABEL_24;
  }
  v28 = 1688;
  v13 = 1690;
  if ( !a5 )
  {
    LastFailureAsHRESULT = -1996488695;
    goto LABEL_23;
  }
  v27 = 0;
  v28 = 1690;
  FileW = CreateFileW(a2, 0xC0000000, 3u, 0, 3u, 0x20000080u, 0);
  v19 = (char *)*((_QWORD *)this + 9);
  if ( (unsigned __int64)(v19 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v19);
  *((_QWORD *)this + 9) = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v19, v15, v17, v18);
    v27 = LastFailureAsHRESULT;
    v13 = 1700;
LABEL_24:
    v29 = v13;
    goto LABEL_25;
  }
  v27 = 0;
  v28 = 1700;
  *((_QWORD *)this + 10) = a3;
  *((_QWORD *)this + 6) = a5;
  *((_QWORD *)this + 7) = a6;
  *((_DWORD *)this + 16) = a4;
  *((_DWORD *)this + 26) = a9;
  *((_DWORD *)this + 22) = (a5 + a3 + ~a6) / a5;
  v20 = (a3 - a6) % a5 != 0;
  v21 = 0;
  if ( !a9 )
    v21 = v20;
  v22 = (CFreeSlabManagerDelegate *)operator new(0x1C8u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v22
    || (v23 = CFreeSlabManagerDelegate::CFreeSlabManagerDelegate(
                v22,
                *((_DWORD *)this + 22),
                *((_QWORD *)this + 6),
                *((_QWORD *)this + 7),
                *((_DWORD *)this + 16),
                v21,
                *((_DWORD *)this + 26) != 0),
        (v24 = v23) == 0) )
  {
    LastFailureAsHRESULT = -2147024882;
    v13 = 1743;
    goto LABEL_23;
  }
  v27 = 0;
  v28 = 1743;
  v25 = *(__int64 (__fastcall ***)(CFreeSlabManagerDelegate *))v23;
  if ( a9 )
  {
    LastFailureAsHRESULT = v25[1](v24);
    v27 = LastFailureAsHRESULT;
    v13 = 1750;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_24;
    v28 = 1750;
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(CFreeSlabManagerDelegate *, _QWORD, _QWORD))(*(_QWORD *)v24 + 168LL))(
                             v24,
                             *((_QWORD *)this + 9),
                             *((_QWORD *)this + 10));
    v27 = LastFailureAsHRESULT;
    v13 = 1751;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_24;
    v28 = 1751;
    *((_QWORD *)this + 5) = v24;
  }
  else
  {
    LastFailureAsHRESULT = (*v25)(v24);
    v27 = LastFailureAsHRESULT;
    v13 = 1759;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_24;
    v28 = 1759;
    if ( v21 )
      (*(void (__fastcall **)(CFreeSlabManagerDelegate *, _QWORD))(*(_QWORD *)v24 + 72LL))(
        v24,
        (unsigned int)(*((_DWORD *)this + 22) - 1));
    *((_QWORD *)this + 5) = v24;
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(CFreeSlabManager *, _QWORD))(*(_QWORD *)this + 24LL))(this, 0);
    v27 = LastFailureAsHRESULT;
    v13 = 1781;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_24;
    v28 = 1781;
  }
LABEL_25:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v27);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18003dad4  push    rbp
0x18003dad6  push    rbx
0x18003dad7  push    rsi
0x18003dad8  push    rdi
0x18003dad9  push    r14
0x18003dadb  push    r15
0x18003dadd  lea     rbp, [rsp-7]
0x18003dae2  sub     rsp, 88h
0x18003dae9  mov     r15d, r9d
0x18003daec  mov     r14, r8
0x18003daef  mov     rbx, rdx
0x18003daf2  mov     rdi, rcx
0x18003daf5  mov     r9d, 1; unsigned __int16
0x18003dafb  mov     r8d, 695h; unsigned __int16
0x18003db01  lea     rdx, aCfreeslabmanag_20; "CFreeSlabManager::_Initialize"
0x18003db08  lea     rcx, [rbp+2Fh+var_70]; this
0x18003db0c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18003db11  nop
0x18003db12  mov     eax, 698h
0x18003db17  test    rbx, rbx
0x18003db1a  jnz     short loc_18003DB26
0x18003db1c  mov     ebx, 80070057h
0x18003db21  jmp     loc_18003DD35
0x18003db26  mov     [rbp+2Fh+var_6C], ax
0x18003db2a  mov     rsi, [rbp+2Fh+arg_20]
0x18003db2e  mov     eax, 69Ah
0x18003db33  test    rsi, rsi
0x18003db36  jnz     short loc_18003DB42
0x18003db38  mov     ebx, 89000009h
0x18003db3d  jmp     loc_18003DD35
0x18003db42  mov     [rbp+2Fh+var_70], 0
0x18003db49  mov     [rbp+2Fh+var_6C], ax
0x18003db4d  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x18003db56  mov     [rsp+0B0h+dwFlagsAndAttributes], 20000080h; dwFlagsAndAttributes
0x18003db5e  mov     r8d, 3; dwShareMode
0x18003db64  mov     [rsp+0B0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18003db69  xor     r9d, r9d; lpSecurityAttributes
0x18003db6c  mov     edx, 0C0000000h; dwDesiredAccess
0x18003db71  mov     rcx, rbx; lpFileName
0x18003db74  call    cs:__imp_CreateFileW
0x18003db7a  mov     rbx, rax
0x18003db7d  mov     rcx, [rdi+48h]; hObject
0x18003db81  lea     rax, [rcx-1]
0x18003db85  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003db89  ja      short loc_18003DB91
0x18003db8b  call    cs:__imp_CloseHandle
0x18003db91  mov     [rdi+48h], rbx
0x18003db95  lea     rax, [rbx+1]
0x18003db99  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003db9f  jnz     short loc_18003DBB5
0x18003dba1  call    GetLastFailureAsHRESULT
0x18003dba6  mov     ebx, eax
0x18003dba8  mov     [rbp+2Fh+var_70], eax
0x18003dbab  mov     eax, 6A4h
0x18003dbb0  jmp     loc_18003DD38
0x18003dbb5  mov     [rbp+2Fh+var_70], 0
0x18003dbbc  mov     eax, 6A4h
0x18003dbc1  mov     [rbp+2Fh+var_6C], ax
0x18003dbc5  mov     [rdi+50h], r14
0x18003dbc9  mov     [rdi+30h], rsi
0x18003dbcd  mov     rcx, [rbp+2Fh+arg_28]
0x18003dbd1  mov     [rdi+38h], rcx
0x18003dbd5  mov     [rdi+40h], r15d
0x18003dbd9  mov     ebx, [rbp+2Fh+arg_40]
0x18003dbdc  mov     [rdi+68h], ebx
0x18003dbdf  mov     rax, rcx
0x18003dbe2  not     rax
0x18003dbe5  add     rax, r14
0x18003dbe8  add     rax, rsi
0x18003dbeb  xor     edx, edx
0x18003dbed  div     rsi
0x18003dbf0  mov     [rdi+58h], eax
0x18003dbf3  sub     r14, rcx
0x18003dbf6  xor     edx, edx
0x18003dbf8  mov     rax, r14
0x18003dbfb  div     rsi
0x18003dbfe  test    rdx, rdx
0x18003dc01  setnz   al
0x18003dc04  xor     r14d, r14d
0x18003dc07  movzx   ecx, al
0x18003dc0a  test    ebx, ebx
0x18003dc0c  cmovz   r14d, ecx
0x18003dc10  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003dc17  mov     ecx, 1C8h; unsigned __int64
0x18003dc1c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003dc21  mov     rcx, rax; this
0x18003dc24  mov     [rbp+2Fh+arg_8], rax
0x18003dc28  test    rax, rax
0x18003dc2b  jz      loc_18003DD2B
0x18003dc31  cmp     dword ptr [rdi+68h], 0
0x18003dc35  setnz   al
0x18003dc38  mov     byte ptr [rsp+0B0h+hTemplateFile], al; bool
0x18003dc3c  mov     byte ptr [rsp+0B0h+dwFlagsAndAttributes], r14b; bool
0x18003dc41  mov     eax, [rdi+40h]
0x18003dc44  mov     [rsp+0B0h+dwCreationDisposition], eax; unsigned int
0x18003dc48  mov     r9, [rdi+38h]; unsigned __int64
0x18003dc4c  mov     r8, [rdi+30h]; unsigned __int64
0x18003dc50  mov     edx, [rdi+58h]; unsigned int
0x18003dc53  call    ??0CFreeSlabManagerDelegate@@QEAA@K_K0K_N1@Z; CFreeSlabManagerDelegate::CFreeSlabManagerDelegate(ulong,unsigned __int64,unsigned __int64,ulong,bool,bool)
0x18003dc58  mov     rsi, rax
0x18003dc5b  test    rax, rax
0x18003dc5e  jz      loc_18003DD2B
0x18003dc64  mov     [rbp+2Fh+var_70], 0
0x18003dc6b  mov     eax, 6CFh
0x18003dc70  mov     [rbp+2Fh+var_6C], ax
0x18003dc74  mov     rax, [rsi]
0x18003dc77  mov     rcx, rsi
0x18003dc7a  test    ebx, ebx
0x18003dc7c  jz      short loc_18003DCCF
0x18003dc7e  mov     rax, [rax+8]
0x18003dc82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc87  mov     ebx, eax
0x18003dc89  mov     [rbp+2Fh+var_70], eax
0x18003dc8c  test    eax, eax
0x18003dc8e  mov     eax, 6D6h
0x18003dc93  js      loc_18003DD38
0x18003dc99  mov     [rbp+2Fh+var_6C], ax
0x18003dc9d  mov     rax, [rsi]
0x18003dca0  mov     r8, [rdi+50h]
0x18003dca4  mov     rdx, [rdi+48h]
0x18003dca8  mov     rcx, rsi
0x18003dcab  mov     rax, [rax+0A8h]
0x18003dcb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dcb7  mov     ebx, eax
0x18003dcb9  mov     [rbp+2Fh+var_70], eax
0x18003dcbc  test    eax, eax
0x18003dcbe  mov     eax, 6D7h
0x18003dcc3  js      short loc_18003DD38
0x18003dcc5  mov     [rbp+2Fh+var_6C], ax
0x18003dcc9  mov     [rdi+28h], rsi
0x18003dccd  jmp     short loc_18003DD3C
0x18003dccf  mov     rax, [rax]
0x18003dcd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dcd7  mov     ebx, eax
0x18003dcd9  mov     [rbp+2Fh+var_70], eax
0x18003dcdc  test    eax, eax
0x18003dcde  mov     eax, 6DFh
0x18003dce3  js      short loc_18003DD38
0x18003dce5  mov     [rbp+2Fh+var_6C], ax
0x18003dce9  test    r14b, r14b
0x18003dcec  jz      short loc_18003DD02
0x18003dcee  mov     rax, [rsi]
0x18003dcf1  mov     edx, [rdi+58h]
0x18003dcf4  dec     edx
0x18003dcf6  mov     rcx, rsi
0x18003dcf9  mov     rax, [rax+48h]
0x18003dcfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd02  mov     [rdi+28h], rsi
0x18003dd06  mov     rax, [rdi]
0x18003dd09  xor     edx, edx
0x18003dd0b  mov     rcx, rdi
0x18003dd0e  mov     rax, [rax+18h]
0x18003dd12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd17  mov     ebx, eax
0x18003dd19  mov     [rbp+2Fh+var_70], eax
0x18003dd1c  test    eax, eax
0x18003dd1e  mov     eax, 6F5h
0x18003dd23  js      short loc_18003DD38
0x18003dd25  mov     [rbp+2Fh+var_6C], ax
0x18003dd29  jmp     short loc_18003DD3C
0x18003dd2b  mov     ebx, 8007000Eh
0x18003dd30  mov     eax, 6CFh
0x18003dd35  mov     [rbp+2Fh+var_70], ebx
0x18003dd38  mov     [rbp+2Fh+var_6A], ax
0x18003dd3c  lea     rcx, [rbp+2Fh+var_70]; this
0x18003dd40  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18003dd45  mov     eax, ebx
0x18003dd47  add     rsp, 88h
0x18003dd4e  pop     r15
0x18003dd50  pop     r14
0x18003dd52  pop     rdi
0x18003dd53  pop     rsi
0x18003dd54  pop     rbx
0x18003dd55  pop     rbp
0x18003dd56  retn
```
