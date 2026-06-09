# TLSRpcGetServerNameFixed

- ea: `0x180013780`
- end: `0x1800138f3`
- name: `TLSRpcGetServerNameFixed`
- size: `371`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int16 **, DWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000cff0`
- `0x180013780`
- `0x18001ae3c`
- `0x180044fc8`
- `0x1800a0fb0`

## import_xrefs

- `KERNEL32!GetComputerNameW` at `0x180013837`
- `KERNEL32!GetComputerNameW` at `0x180013837`
- `KERNEL32!GetLastError` at `0x180013847`
- `KERNEL32!GetLastError` at `0x180013847`
- `KERNEL32!LocalAlloc` at `0x180013863`
- `KERNEL32!LocalAlloc` at `0x180013863`

## pseudocode

```c
__int64 __fastcall TLSRpcGetServerNameFixed(_QWORD *a1, unsigned __int16 **a2, DWORD *a3)
{
  PVOID *v6; // rcx
  DWORD LastError; // eax
  unsigned __int16 *v8; // rax
  DWORD nSize; // [rsp+20h] [rbp-48h] BYREF
  WCHAR Buffer[16]; // [rsp+28h] [rbp-40h] BYREF

  nSize = 16;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
  {
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      118,
      &WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
      L"TLSRpcGetServerNameFixed");
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 || !a2 || !a3 )
    return 87;
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
    WPP_SF_S(v6[2], 119, &WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids, *a1);
  *a2 = 0;
  if ( !GetComputerNameW(Buffer, &nSize) )
  {
    LastError = GetLastError();
LABEL_15:
    *a3 = LastError;
    goto LABEL_16;
  }
  v8 = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * (nSize + 1));
  *a2 = v8;
  if ( !v8 )
  {
    LastError = TLSMapReturnCode(4117);
    goto LABEL_15;
  }
  StringCchCopyW(v8, nSize + 1, Buffer);
  *a3 = 0;
LABEL_16:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      120,
      &WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
      L"TLSRpcGetServerNameFixed");
  return 0;
}

```

## disassembly

```asm
0x180013780  mov     [rsp+arg_18], rbx
0x180013785  push    rbp
0x180013786  push    rsi
0x180013787  push    rdi
0x180013788  sub     rsp, 50h
0x18001378c  mov     rax, cs:__security_cookie
0x180013793  xor     rax, rsp
0x180013796  mov     [rsp+68h+var_20], rax
0x18001379b  mov     rbx, r8
0x18001379e  mov     [rsp+68h+nSize], 10h
0x1800137a6  mov     rdi, rdx
0x1800137a9  mov     rsi, rcx
0x1800137ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800137b3  lea     rbp, WPP_GLOBAL_Control
0x1800137ba  cmp     rcx, rbp
0x1800137bd  jz      short loc_1800137EB
0x1800137bf  test    dword ptr [rcx+1Ch], 1000h
0x1800137c6  jz      short loc_1800137EB
0x1800137c8  mov     rcx, [rcx+10h]
0x1800137cc  lea     r9, aTlsrpcgetserve_3; "TLSRpcGetServerNameFixed"
0x1800137d3  mov     edx, 76h ; 'v'
0x1800137d8  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x1800137df  call    WPP_SF_S
0x1800137e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800137eb  test    rsi, rsi
0x1800137ee  jz      loc_1800138D0
0x1800137f4  test    rdi, rdi
0x1800137f7  jz      loc_1800138D0
0x1800137fd  test    rbx, rbx
0x180013800  jz      loc_1800138D0
0x180013806  cmp     rcx, rbp
0x180013809  jz      short loc_180013829
0x18001380b  test    byte ptr [rcx+1Ch], 20h
0x18001380f  jz      short loc_180013829
0x180013811  mov     r9, [rsi]
0x180013814  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x18001381b  mov     rcx, [rcx+10h]
0x18001381f  mov     edx, 77h ; 'w'
0x180013824  call    WPP_SF_S
0x180013829  and     qword ptr [rdi], 0
0x18001382d  lea     rdx, [rsp+68h+nSize]; nSize
0x180013832  lea     rcx, [rsp+68h+Buffer]; lpBuffer
0x180013837  call    cs:__imp_GetComputerNameW
0x18001383e  nop     dword ptr [rax+rax+00h]
0x180013843  test    eax, eax
0x180013845  jnz     short loc_180013855
0x180013847  call    cs:__imp_GetLastError
0x18001384e  nop     dword ptr [rax+rax+00h]
0x180013853  jmp     short loc_180013899
0x180013855  mov     edx, [rsp+68h+nSize]
0x180013859  mov     ecx, 40h ; '@'; uFlags
0x18001385e  inc     edx
0x180013860  add     rdx, rdx; uBytes
0x180013863  call    cs:__imp_LocalAlloc
0x18001386a  nop     dword ptr [rax+rax+00h]
0x18001386f  mov     [rdi], rax
0x180013872  test    rax, rax
0x180013875  jz      short loc_18001388F
0x180013877  mov     edx, [rsp+68h+nSize]
0x18001387b  lea     r8, [rsp+68h+Buffer]; unsigned __int16 *
0x180013880  inc     edx; unsigned __int64
0x180013882  mov     rcx, rax; unsigned __int16 *
0x180013885  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001388a  and     dword ptr [rbx], 0
0x18001388d  jmp     short loc_18001389B
0x18001388f  mov     ecx, 1015h
0x180013894  call    TLSMapReturnCode
0x180013899  mov     [rbx], eax
0x18001389b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800138a2  cmp     rcx, rbp
0x1800138a5  jz      short loc_1800138CC
0x1800138a7  test    dword ptr [rcx+1Ch], 1000h
0x1800138ae  jz      short loc_1800138CC
0x1800138b0  mov     rcx, [rcx+10h]
0x1800138b4  lea     r9, aTlsrpcgetserve_3; "TLSRpcGetServerNameFixed"
0x1800138bb  mov     edx, 78h ; 'x'
0x1800138c0  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x1800138c7  call    WPP_SF_S
0x1800138cc  xor     eax, eax
0x1800138ce  jmp     short loc_1800138D5
0x1800138d0  mov     eax, 57h ; 'W'
0x1800138d5  mov     rcx, [rsp+68h+var_20]
0x1800138da  xor     rcx, rsp; StackCookie
0x1800138dd  call    __security_check_cookie
0x1800138e2  mov     rbx, [rsp+68h+arg_18]
0x1800138ea  add     rsp, 50h
0x1800138ee  pop     rdi
0x1800138ef  pop     rsi
0x1800138f0  pop     rbp
0x1800138f1  retn
```
