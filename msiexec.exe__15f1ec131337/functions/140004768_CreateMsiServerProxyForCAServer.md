# CreateMsiServerProxyForCAServer

- ea: `0x140004768`
- end: `0x14000485b`
- name: `CreateMsiServerProxyForCAServer`
- size: `243`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1400011e4`

## callees

- `0x140003883`
- `0x140004768`
- `0x140007110`
- `0x1400088c0`
- `0x140009820`
- `0x14000a010`

## pseudocode

```c
__int64 CreateMsiServerProxyForCAServer()
{
  unsigned int v0; // ebx
  __int64 result; // rax
  __int64 v2; // [rsp+30h] [rbp-F8h] BYREF
  __int64 v3; // [rsp+38h] [rbp-F0h] BYREF
  BYTE Data[2]; // [rsp+40h] [rbp-E8h] BYREF
  _BYTE v5[206]; // [rsp+42h] [rbp-E6h] BYREF

  v2 = 0;
  v0 = ((__int64 (__fastcall *)(GUID *, _QWORD, __int64, GUID *, __int64 *))OLE32::CoCreateInstance)(
         &IID_IMsiServer,
         0,
         4,
         &IID_IUnknown,
         &v2);
  if ( v0 )
  {
    *(_WORD *)Data = 0;
    memset_0(v5, 0, 0xC6u);
    if ( (int)StringCchPrintfW((unsigned __int16 *)Data, 0x64u, L"Failed to connect to server. Error: 0x%X", v0) >= 0 )
      ReportErrorToDebugOutput(Data, 0);
  }
  else
  {
    v3 = 0;
    (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v2)(v2, &IID_IMsiServer, &v3);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    result = v3;
    if ( v3 )
      return result;
  }
  return 0;
}

```

## disassembly

```asm
0x140004768  push    rbx
0x14000476a  sub     rsp, 120h
0x140004771  mov     rax, cs:__security_cookie
0x140004778  xor     rax, rsp
0x14000477b  mov     [rsp+128h+var_18], rax
0x140004783  xor     edx, edx
0x140004785  mov     [rsp+128h+var_F8], 0
0x14000478e  lea     rax, [rsp+128h+var_F8]
0x140004793  mov     [rsp+128h+var_108], rax
0x140004798  lea     r9, IID_IUnknown
0x14000479f  mov     rax, cs:?CoCreateInstance@OLE32@@3P6AJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@ZEA; long (*OLE32::CoCreateInstance)(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x1400047a6  lea     rcx, IID_IMsiServer
0x1400047ad  lea     r8d, [rdx+4]
0x1400047b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400047b6  mov     ebx, eax
0x1400047b8  test    eax, eax
0x1400047ba  jz      short loc_140004800
0x1400047bc  xor     ecx, ecx
0x1400047be  xor     edx, edx; Val
0x1400047c0  mov     word ptr [rsp+128h+Data], cx
0x1400047c5  mov     r8d, 0C6h; Size
0x1400047cb  lea     rcx, [rsp+128h+var_E6]; void *
0x1400047d0  call    memset_0
0x1400047d5  mov     r9d, ebx
0x1400047d8  lea     r8, aFailedToConnec; "Failed to connect to server. Error: 0x%"...
0x1400047df  mov     edx, 64h ; 'd'; unsigned __int64
0x1400047e4  lea     rcx, [rsp+128h+Data]; unsigned __int16 *
0x1400047e9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400047ee  test    eax, eax
0x1400047f0  js      short loc_140004840
0x1400047f2  xor     edx, edx; unsigned int
0x1400047f4  lea     rcx, [rsp+128h+Data]; lpData
0x1400047f9  call    ?ReportErrorToDebugOutput@@YAXPEBGK@Z; ReportErrorToDebugOutput(ushort const *,ulong)
0x1400047fe  jmp     short loc_140004840
0x140004800  mov     rcx, [rsp+128h+var_F8]
0x140004805  lea     r8, [rsp+128h+var_F0]
0x14000480a  mov     [rsp+128h+var_F0], 0
0x140004813  lea     rdx, IID_IMsiServer
0x14000481a  mov     rax, [rcx]
0x14000481d  mov     rax, [rax]
0x140004820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004825  mov     rcx, [rsp+128h+var_F8]
0x14000482a  mov     rax, [rcx]
0x14000482d  mov     rax, [rax+10h]
0x140004831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004836  mov     rax, [rsp+128h+var_F0]
0x14000483b  test    rax, rax
0x14000483e  jnz     short loc_140004842
0x140004840  xor     eax, eax
0x140004842  mov     rcx, [rsp+128h+var_18]
0x14000484a  xor     rcx, rsp; StackCookie
0x14000484d  call    __security_check_cookie
0x140004852  add     rsp, 120h
0x140004859  pop     rbx
0x14000485a  retn
```
