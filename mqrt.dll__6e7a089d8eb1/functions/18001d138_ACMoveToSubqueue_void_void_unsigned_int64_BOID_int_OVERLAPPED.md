# ACMoveToSubqueue(void *,void *,unsigned __int64 *,BOID *,int,_OVERLAPPED *)

- ea: `0x18001d138`
- end: `0x18001d21e`
- name: `?ACMoveToSubqueue@@YAJPEAX0PEA_KPEAUBOID@@HPEAU_OVERLAPPED@@@Z`
- size: `230`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, void *@<rdx>, unsigned __int64 *@<r8>, struct BOID *@<r9>, int, struct _OVERLAPPED *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001d224`

## callees

- `0x1800056e8`
- `0x18001d138`
- `0x180023ca0`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x18001d203`
- `ntdll!NtDeviceIoControlFile` at `0x18001d203`

## pseudocode

```c
NTSTATUS __fastcall ACMoveToSubqueue(
        void *a1,
        void *a2,
        unsigned __int64 *a3,
        struct BOID *a4,
        int a5,
        struct _OVERLAPPED *a6)
{
  __int64 InputBuffer; // [rsp+50h] [rbp-38h] BYREF
  __int128 v8; // [rsp+58h] [rbp-30h]
  void *v9; // [rsp+68h] [rbp-20h]
  int v10; // [rsp+70h] [rbp-18h]

  v9 = a2;
  v10 = a5;
  v8 = 0;
  if ( a4 )
    v8 = (__int128)*a4;
  else
    v8 = 0;
  if ( a3 )
    InputBuffer = *a3;
  else
    InputBuffer = 0;
  if ( a6 )
    return MQpDeviceIoControl(a1, 0x1965414Fu, &InputBuffer, 0x24u, 0, 0, a6);
  else
    return NtDeviceIoControlFile(a1, 0, 0, 0, &`MQpDeviceIoControl'::`2'::Iosb, 0x1965414Fu, &InputBuffer, 0x24u, 0, 0);
}

```

## disassembly

```asm
0x18001d138  sub     rsp, 88h
0x18001d13f  mov     rax, cs:__security_cookie
0x18001d146  xor     rax, rsp
0x18001d149  mov     [rsp+88h+var_10], rax
0x18001d14e  mov     eax, [rsp+88h+arg_20]
0x18001d155  xorps   xmm0, xmm0
0x18001d158  mov     [rsp+88h+var_20], rdx
0x18001d15d  mov     r10, rcx
0x18001d160  mov     rcx, [rsp+88h+arg_28]
0x18001d168  xor     edx, edx; Event
0x18001d16a  mov     [rsp+88h+var_18], eax
0x18001d16e  movdqu  [rsp+88h+var_30], xmm0
0x18001d174  test    r9, r9
0x18001d177  jz      short loc_18001D185
0x18001d179  movups  xmm0, xmmword ptr [r9]
0x18001d17d  movdqu  [rsp+88h+var_30], xmm0
0x18001d183  jmp     short loc_18001D18A
0x18001d185  movups  [rsp+88h+var_30], xmm0
0x18001d18a  test    r8, r8
0x18001d18d  jz      short loc_18001D199
0x18001d18f  mov     rax, [r8]
0x18001d192  mov     [rsp+88h+var_38], rax
0x18001d197  jmp     short loc_18001D19E
0x18001d199  mov     [rsp+88h+var_38], rdx
0x18001d19e  test    rcx, rcx
0x18001d1a1  jz      short loc_18001D1CB
0x18001d1a3  mov     [rsp+88h+InputBuffer], rcx; struct _OVERLAPPED *
0x18001d1a8  lea     r8, [rsp+88h+var_38]; void *
0x18001d1ad  mov     [rsp+88h+IoControlCode], edx; unsigned int
0x18001d1b1  mov     r9d, 24h ; '$'; unsigned int
0x18001d1b7  mov     [rsp+88h+IoStatusBlock], rdx; void *
0x18001d1bc  mov     rcx, r10; void *
0x18001d1bf  mov     edx, 1965414Fh; unsigned int
0x18001d1c4  call    ?MQpDeviceIoControl@@YAJPEAXK0K0KPEAU_OVERLAPPED@@@Z; MQpDeviceIoControl(void *,ulong,void *,ulong,void *,ulong,_OVERLAPPED *)
0x18001d1c9  jmp     short loc_18001D209
0x18001d1cb  mov     [rsp+88h+OutputBufferLength], edx; OutputBufferLength
0x18001d1cf  lea     rax, [rsp+88h+var_38]
0x18001d1d4  mov     [rsp+88h+OutputBuffer], rdx; OutputBuffer
0x18001d1d9  xor     r9d, r9d; ApcContext
0x18001d1dc  mov     [rsp+88h+InputBufferLength], 24h ; '$'; InputBufferLength
0x18001d1e4  xor     r8d, r8d; ApcRoutine
0x18001d1e7  mov     [rsp+88h+InputBuffer], rax; InputBuffer
0x18001d1ec  mov     rcx, r10; FileHandle
0x18001d1ef  lea     rax, ?Iosb@?1??MQpDeviceIoControl@@YAJPEAXK0K0K@Z@4U_IO_STATUS_BLOCK@@A; _IO_STATUS_BLOCK `MQpDeviceIoControl(void *,ulong,void *,ulong,void *,ulong)'::`2'::Iosb
0x18001d1f6  mov     [rsp+88h+IoControlCode], 1965414Fh; IoControlCode
0x18001d1fe  mov     [rsp+88h+IoStatusBlock], rax; IoStatusBlock
0x18001d203  call    cs:__imp_NtDeviceIoControlFile
0x18001d209  mov     rcx, [rsp+88h+var_10]
0x18001d20e  xor     rcx, rsp; StackCookie
0x18001d211  call    __security_check_cookie
0x18001d216  add     rsp, 88h
0x18001d21d  retn
```
