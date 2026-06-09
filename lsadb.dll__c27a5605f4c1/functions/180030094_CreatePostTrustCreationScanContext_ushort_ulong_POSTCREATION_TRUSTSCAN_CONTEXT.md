# CreatePostTrustCreationScanContext(ushort *,ulong,_POSTCREATION_TRUSTSCAN_CONTEXT * *)

- ea: `0x180030094`
- end: `0x180030197`
- name: `?CreatePostTrustCreationScanContext@@YAJPEAGKPEAPEAU_POSTCREATION_TRUSTSCAN_CONTEXT@@@Z`
- size: `259`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, struct _POSTCREATION_TRUSTSCAN_CONTEXT **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180030854`

## callees

- `0x180001670`
- `0x18002fe60`
- `0x180030094`
- `0x180030650`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180030151`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180030151`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800300d8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800300d8`
- `RPCRT4!UuidCreate` at `0x18003010d`
- `RPCRT4!UuidCreate` at `0x18003010d`
- `RPCRT4!UuidToStringW` at `0x180030128`
- `RPCRT4!UuidToStringW` at `0x180030128`
- `RPCRT4!RpcStringFreeW` at `0x18003016c`
- `RPCRT4!RpcStringFreeW` at `0x18003016c`

## pseudocode

```c
__int64 __fastcall CreatePostTrustCreationScanContext(unsigned __int16 *a1, int a2, unsigned __int16 ***a3)
{
  unsigned __int16 **v6; // rax
  unsigned __int16 **v7; // rdi
  int v8; // ebx
  RPC_STATUS v9; // eax
  unsigned __int16 *EventW; // rax
  RPC_WSTR StringUuid; // [rsp+20h] [rbp-38h] BYREF
  UUID Uuid; // [rsp+28h] [rbp-30h] BYREF

  StringUuid = 0;
  *a3 = 0;
  Uuid = 0;
  v6 = (unsigned __int16 **)LocalAlloc(0x40u, 0x30u);
  v7 = v6;
  if ( v6 )
  {
    *(_DWORD *)v6 = 0;
    *((_DWORD *)v6 + 4) = a2;
    v8 = LsaDbCopyString(a1, v6 + 1);
    if ( v8 < 0 )
      goto LABEL_10;
    v9 = UuidCreate(&Uuid);
    if ( (!v9 || v9 == 1824) && !UuidToStringW(&Uuid, &StringUuid) )
    {
      v8 = LsaDbCopyString(StringUuid, v7 + 4);
      if ( v8 < 0 )
        goto LABEL_10;
      EventW = (unsigned __int16 *)CreateEventW(0, 0, 0, v7[4]);
      v7[3] = EventW;
      if ( EventW )
      {
        *a3 = v7;
        v7 = 0;
        v8 = 0;
        goto LABEL_10;
      }
    }
  }
  v8 = -1073741801;
LABEL_10:
  RpcStringFreeW(&StringUuid);
  FreePostTrustCreationScanContext(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180030094  mov     [rsp+arg_8], rbx
0x180030099  push    rsi
0x18003009a  push    rdi
0x18003009b  push    r14
0x18003009d  sub     rsp, 40h
0x1800300a1  mov     rax, cs:__security_cookie
0x1800300a8  xor     rax, rsp
0x1800300ab  mov     [rsp+58h+var_20], rax
0x1800300b0  mov     ebx, edx
0x1800300b2  mov     [rsp+58h+StringUuid], 0
0x1800300bb  mov     edx, 30h ; '0'; uBytes
0x1800300c0  mov     qword ptr [r8], 0
0x1800300c7  mov     rsi, rcx
0x1800300ca  xorps   xmm0, xmm0
0x1800300cd  mov     r14, r8
0x1800300d0  movups  xmmword ptr [rsp+58h+Uuid.Data1], xmm0
0x1800300d5  lea     ecx, [rdx+10h]; uFlags
0x1800300d8  call    cs:__imp_LocalAlloc
0x1800300de  mov     rdi, rax
0x1800300e1  test    rax, rax
0x1800300e4  jnz     short loc_1800300ED
0x1800300e6  mov     ebx, 0C0000017h
0x1800300eb  jmp     short loc_180030167
0x1800300ed  lea     rdx, [rax+8]; unsigned __int16 **
0x1800300f1  mov     dword ptr [rax], 0
0x1800300f7  mov     rcx, rsi; unsigned __int16 *
0x1800300fa  mov     [rax+10h], ebx
0x1800300fd  call    ?LsaDbCopyString@@YAJPEAGPEAPEAG@Z; LsaDbCopyString(ushort *,ushort * *)
0x180030102  mov     ebx, eax
0x180030104  test    eax, eax
0x180030106  js      short loc_180030167
0x180030108  lea     rcx, [rsp+58h+Uuid]; Uuid
0x18003010d  call    cs:__imp_UuidCreate
0x180030113  test    eax, eax
0x180030115  jz      short loc_18003011E
0x180030117  cmp     eax, 720h
0x18003011c  jnz     short loc_1800300E6
0x18003011e  lea     rdx, [rsp+58h+StringUuid]; StringUuid
0x180030123  lea     rcx, [rsp+58h+Uuid]; Uuid
0x180030128  call    cs:__imp_UuidToStringW
0x18003012e  test    eax, eax
0x180030130  jnz     short loc_1800300E6
0x180030132  mov     rcx, [rsp+58h+StringUuid]; unsigned __int16 *
0x180030137  lea     rdx, [rdi+20h]; unsigned __int16 **
0x18003013b  call    ?LsaDbCopyString@@YAJPEAGPEAPEAG@Z; LsaDbCopyString(ushort *,ushort * *)
0x180030140  mov     ebx, eax
0x180030142  test    eax, eax
0x180030144  js      short loc_180030167
0x180030146  mov     r9, [rdi+20h]; lpName
0x18003014a  xor     r8d, r8d; bInitialState
0x18003014d  xor     edx, edx; bManualReset
0x18003014f  xor     ecx, ecx; lpEventAttributes
0x180030151  call    cs:__imp_CreateEventW
0x180030157  mov     [rdi+18h], rax
0x18003015b  test    rax, rax
0x18003015e  jz      short loc_1800300E6
0x180030160  mov     [r14], rdi
0x180030163  xor     edi, edi
0x180030165  xor     ebx, ebx
0x180030167  lea     rcx, [rsp+58h+StringUuid]; String
0x18003016c  call    cs:__imp_RpcStringFreeW
0x180030172  mov     rcx, rdi; hMem
0x180030175  call    ?FreePostTrustCreationScanContext@@YAXPEAU_POSTCREATION_TRUSTSCAN_CONTEXT@@@Z; FreePostTrustCreationScanContext(_POSTCREATION_TRUSTSCAN_CONTEXT *)
0x18003017a  mov     eax, ebx
0x18003017c  mov     rcx, [rsp+58h+var_20]
0x180030181  xor     rcx, rsp; StackCookie
0x180030184  call    __security_check_cookie
0x180030189  mov     rbx, [rsp+58h+arg_8]
0x18003018e  add     rsp, 40h
0x180030192  pop     r14
0x180030194  pop     rdi
0x180030195  pop     rsi
0x180030196  retn
```
