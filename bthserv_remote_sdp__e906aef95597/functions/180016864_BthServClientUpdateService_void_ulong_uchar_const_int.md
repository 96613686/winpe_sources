# BthServClientUpdateService(void *,ulong,uchar * const,int)

- ea: `0x180016864`
- end: `0x18001695c`
- name: `?BthServClientUpdateService@@YAKPEAXKQEAEH@Z`
- size: `248`
- prototype: `__int64 __fastcall(void *, DWORD, unsigned __int8 *const, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180013f10`
- `0x180027ea8`

## callees

- `0x18000dfcc`
- `0x180010128`
- `0x180016864`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001693d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001693d`

## pseudocode

```c
__int64 __fastcall BthServClientUpdateService(void *a1, DWORD a2, unsigned __int8 *const a3, int a4)
{
  unsigned int v8; // edi
  volatile signed __int32 *v9; // rbx
  HANDLE *v10; // [rsp+40h] [rbp-18h] BYREF
  volatile signed __int32 *v11; // [rsp+48h] [rbp-10h]
  DWORD NumberOfBytesTransferred; // [rsp+68h] [rbp+10h] BYREF

  NumberOfBytesTransferred = 0;
  if ( a2 < 0x72A )
    return 122;
  BthServGlobals::GetSafeRadioHandle(&Globals, &v10);
  if ( v10 && (char *)*v10 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    v8 = BthServOverlappedIoctl(*v10, 0x411030u, a3, a2, 0, 0, &NumberOfBytesTransferred);
  else
    v8 = 6;
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
    {
      v9 = v11;
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  if ( !v8 )
  {
    if ( a4 )
      Sleep(0xBB8u);
  }
  return v8;
}

```

## disassembly

```asm
0x180016864  mov     [rsp+arg_0], rbx
0x180016869  mov     [rsp+arg_10], rsi
0x18001686e  push    rdi
0x18001686f  sub     rsp, 50h
0x180016873  and     [rsp+58h+NumberOfBytesTransferred], 0
0x180016878  mov     esi, r9d
0x18001687b  mov     rdi, r8
0x18001687e  mov     ebx, edx
0x180016880  cmp     edx, 72Ah
0x180016886  jnb     short loc_180016892
0x180016888  mov     eax, 7Ah ; 'z'
0x18001688d  jmp     loc_18001694B
0x180016892  lea     rdx, [rsp+58h+var_18]
0x180016897  lea     rcx, ?Globals@@3VBthServGlobals@@A; BthServGlobals Globals
0x18001689e  call    ?GetSafeRadioHandle@BthServGlobals@@QEAA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@XZ; BthServGlobals::GetSafeRadioHandle(void)
0x1800168a3  mov     rax, [rsp+58h+var_18]
0x1800168a8  test    rax, rax
0x1800168ab  jz      short loc_1800168E3
0x1800168ad  mov     rcx, [rax]; hFile
0x1800168b0  lea     rax, [rcx-1]
0x1800168b4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800168b8  ja      short loc_1800168E3
0x1800168ba  lea     rax, [rsp+58h+NumberOfBytesTransferred]
0x1800168bf  mov     r9d, ebx; nInBufferSize
0x1800168c2  mov     [rsp+58h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x1800168c7  mov     r8, rdi; lpInBuffer
0x1800168ca  and     [rsp+58h+var_30], 0
0x1800168cf  mov     edx, 411030h; dwIoControlCode
0x1800168d4  and     [rsp+58h+var_38], 0
0x1800168da  call    ?BthServOverlappedIoctl@@YAKPEAXK0K0KPEAK@Z; BthServOverlappedIoctl(void *,ulong,void *,ulong,void *,ulong,ulong *)
0x1800168df  mov     edi, eax
0x1800168e1  jmp     short loc_1800168E8
0x1800168e3  mov     edi, 6
0x1800168e8  mov     rcx, [rsp+58h+var_10]
0x1800168ed  test    rcx, rcx
0x1800168f0  jz      short loc_180016930
0x1800168f2  or      eax, 0FFFFFFFFh
0x1800168f5  lock xadd [rcx+8], eax
0x1800168fa  cmp     eax, 1
0x1800168fd  jnz     short loc_180016930
0x1800168ff  mov     rbx, [rsp+58h+var_10]
0x180016904  mov     rcx, rbx
0x180016907  mov     rax, [rbx]
0x18001690a  mov     rax, [rax]
0x18001690d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016912  or      eax, 0FFFFFFFFh
0x180016915  lock xadd [rbx+0Ch], eax
0x18001691a  cmp     eax, 1
0x18001691d  jnz     short loc_180016930
0x18001691f  mov     rcx, [rsp+58h+var_10]
0x180016924  mov     rax, [rcx]
0x180016927  mov     rax, [rax+8]
0x18001692b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016930  test    edi, edi
0x180016932  jnz     short loc_180016949
0x180016934  test    esi, esi
0x180016936  jz      short loc_180016949
0x180016938  mov     ecx, 0BB8h; dwMilliseconds
0x18001693d  call    cs:__imp_Sleep
0x180016944  nop     dword ptr [rax+rax+00h]
0x180016949  mov     eax, edi
0x18001694b  mov     rbx, [rsp+58h+arg_0]
0x180016950  mov     rsi, [rsp+58h+arg_10]
0x180016955  add     rsp, 50h
0x180016959  pop     rdi
0x18001695a  retn
```
