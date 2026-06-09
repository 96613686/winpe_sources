# BufferToIStream(uchar *,int,IStream * *)

- ea: `0x1800197e4`
- end: `0x1800198f9`
- name: `?BufferToIStream@@YAJPEAEHPEAPEAUIStream@@@Z`
- size: `277`
- prototype: `__int64 __fastcall(unsigned __int8 *, int, struct IStream **)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180019c60`
- `0x180019db0`
- `0x180019eb0`
- `0x180019ff0`
- `0x18001a150`

## callees

- `0x1800197e4`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001983c`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001983c`

## pseudocode

```c
__int64 __fastcall BufferToIStream(unsigned __int8 *a1, int a2, struct IStream **a3)
{
  __int64 v3; // rsi
  HRESULT StreamOnHGlobal; // ebx
  __int64 v7; // r14
  int v8; // eax
  LPSTREAM v9; // rcx
  int v11; // [rsp+60h] [rbp+18h] BYREF
  __int64 v12; // [rsp+68h] [rbp+20h]

  v3 = a2;
  if ( !a3 || !a1 || a2 < 4 )
    return 2147942487LL;
  *a3 = 0;
  v11 = 0;
  v12 = (unsigned int)a2;
  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, a3);
  if ( StreamOnHGlobal < 0 )
    goto LABEL_17;
  StreamOnHGlobal = ((__int64 (__fastcall *)(_QWORD, __int64))(*a3)->lpVtbl->SetSize)(*a3, v12);
  if ( StreamOnHGlobal < 0 )
    goto LABEL_17;
  v7 = v3;
  do
  {
    v8 = ((__int64 (__fastcall *)(_QWORD, unsigned __int8 *, _QWORD, int *))(*a3)->lpVtbl->Write)(
           *a3,
           &a1[v7 - (unsigned int)v3],
           (unsigned int)v3,
           &v11);
    LODWORD(v3) = v3 - v11;
    StreamOnHGlobal = v8;
  }
  while ( (int)v3 > 0 && v8 >= 0 );
  if ( v8 < 0
    || (v9 = *a3,
        v12 = 0,
        StreamOnHGlobal = ((__int64 (__fastcall *)(LPSTREAM, _QWORD, _QWORD, _QWORD))v9->lpVtbl->Seek)(v9, 0, 0, 0),
        StreamOnHGlobal < 0) )
  {
LABEL_17:
    if ( *a3 )
    {
      ((void (__fastcall *)(_QWORD))(*a3)->lpVtbl->Release)(*a3);
      *a3 = 0;
    }
  }
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x1800197e4  mov     [rsp+arg_0], rbx
0x1800197e9  mov     [rsp+arg_8], rbp
0x1800197ee  push    rsi
0x1800197ef  push    rdi
0x1800197f0  push    r14
0x1800197f2  sub     rsp, 30h
0x1800197f6  movsxd  rsi, edx
0x1800197f9  mov     rdi, r8
0x1800197fc  mov     rbp, rcx
0x1800197ff  test    r8, r8
0x180019802  jz      loc_1800198E1
0x180019808  test    rcx, rcx
0x18001980b  jz      loc_1800198E1
0x180019811  cmp     esi, 4
0x180019814  jl      loc_1800198E1
0x18001981a  mov     edx, 1; fDeleteOnRelease
0x18001981f  mov     qword ptr [r8], 0
0x180019826  xor     ecx, ecx; hGlobal
0x180019828  mov     [rsp+48h+arg_10], 0
0x180019830  mov     dword ptr [rsp+48h+arg_18], esi
0x180019834  mov     dword ptr [rsp+48h+arg_18+4], 0
0x18001983c  call    cs:__imp_CreateStreamOnHGlobal
0x180019842  mov     ebx, eax
0x180019844  test    eax, eax
0x180019846  js      short loc_1800198C2
0x180019848  mov     rcx, [rdi]
0x18001984b  mov     rdx, [rsp+48h+arg_18]
0x180019850  mov     rax, [rcx]
0x180019853  mov     rax, [rax+30h]
0x180019857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001985c  mov     ebx, eax
0x18001985e  test    eax, eax
0x180019860  js      short loc_1800198C2
0x180019862  mov     r14, rsi
0x180019865  mov     rcx, [rdi]
0x180019868  lea     r9, [rsp+48h+arg_10]
0x18001986d  mov     eax, esi
0x18001986f  mov     rdx, r14
0x180019872  sub     rdx, rax
0x180019875  add     rdx, rbp
0x180019878  mov     r8, [rcx]
0x18001987b  mov     rax, [r8+20h]
0x18001987f  mov     r8d, esi
0x180019882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019887  sub     esi, [rsp+48h+arg_10]
0x18001988b  mov     ebx, eax
0x18001988d  test    esi, esi
0x18001988f  jle     short loc_180019895
0x180019891  test    eax, eax
0x180019893  jns     short loc_180019865
0x180019895  test    eax, eax
0x180019897  js      short loc_1800198C2
0x180019899  mov     rcx, [rdi]
0x18001989c  xor     r9d, r9d
0x18001989f  mov     [rsp+48h+arg_18], 0
0x1800198a8  xor     r8d, r8d
0x1800198ab  mov     rdx, [rsp+48h+arg_18]
0x1800198b0  mov     rax, [rcx]
0x1800198b3  mov     rax, [rax+28h]
0x1800198b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198bc  mov     ebx, eax
0x1800198be  test    eax, eax
0x1800198c0  jns     short loc_1800198DD
0x1800198c2  mov     rcx, [rdi]
0x1800198c5  test    rcx, rcx
0x1800198c8  jz      short loc_1800198DD
0x1800198ca  mov     rax, [rcx]
0x1800198cd  mov     rax, [rax+10h]
0x1800198d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198d6  mov     qword ptr [rdi], 0
0x1800198dd  mov     eax, ebx
0x1800198df  jmp     short loc_1800198E6
0x1800198e1  mov     eax, 80070057h
0x1800198e6  mov     rbx, [rsp+48h+arg_0]
0x1800198eb  mov     rbp, [rsp+48h+arg_8]
0x1800198f0  add     rsp, 30h
0x1800198f4  pop     r14
0x1800198f6  pop     rdi
0x1800198f7  pop     rsi
0x1800198f8  retn
```
