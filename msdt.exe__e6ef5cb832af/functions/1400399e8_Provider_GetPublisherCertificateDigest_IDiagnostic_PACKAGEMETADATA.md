# Provider::GetPublisherCertificateDigest(IDiagnostic *,_PACKAGEMETADATA *)

- ea: `0x1400399e8`
- end: `0x140039b55`
- name: `?GetPublisherCertificateDigest@Provider@@IEAAJPEAUIDiagnostic@@PEAU_PACKAGEMETADATA@@@Z`
- size: `365`
- prototype: `__int64 __fastcall(SAFEARRAY *this, struct IDiagnostic *, struct _PACKAGEMETADATA *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140039c7c`

## callees

- `0x140020420`
- `0x1400399e8`
- `0x140063010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140039aab`
- `KERNEL32!HeapAlloc` at `0x140039aab`
- `KERNEL32!HeapFree` at `0x140039b06`
- `KERNEL32!HeapFree` at `0x140039b06`
- `KERNEL32!GetProcessHeap` at `0x140039a96`
- `KERNEL32!GetProcessHeap` at `0x140039af2`
- `KERNEL32!GetProcessHeap` at `0x140039a96`
- `KERNEL32!GetProcessHeap` at `0x140039af2`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140039b39`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140039b39`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140039a60`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140039a60`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140039b23`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140039b23`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Provider::GetPublisherCertificateDigest(
        SAFEARRAY *this,
        struct IDiagnostic *a2,
        struct _PACKAGEMETADATA *a3)
{
  __int64 v3; // rax
  HRESULT v5; // eax
  unsigned int v6; // ebx
  int v7; // r9d
  HANDLE ProcessHeap; // rax
  _BYTE *v9; // rdi
  __int64 i; // rdx
  void *v11; // rsi
  HANDLE v12; // rax
  SAFEARRAY *psa; // [rsp+50h] [rbp+8h] BYREF
  void *ppvData; // [rsp+58h] [rbp+10h] BYREF

  psa = this;
  v3 = *(_QWORD *)a2;
  psa = 0;
  ppvData = 0;
  v5 = (*(__int64 (__fastcall **)(struct IDiagnostic *, SAFEARRAY **))(v3 + 96))(a2, &psa);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 444;
LABEL_3:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Provider::GetPublisherCertificateDigest", v7, v5);
    goto LABEL_17;
  }
  if ( !psa )
    goto LABEL_17;
  v5 = SafeArrayAccessData(psa, &ppvData);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 448;
    goto LABEL_3;
  }
  if ( psa->rgsabound[0].cElements == 20 )
  {
    ProcessHeap = GetProcessHeap();
    v9 = HeapAlloc(ProcessHeap, 0, 0x14u);
    if ( v9 )
    {
      for ( i = 0; i != 20; ++i )
        v9[i] = *((_BYTE *)ppvData + i);
      v11 = (void *)*((_QWORD *)a3 + 10);
      if ( v11 )
      {
        v12 = GetProcessHeap();
        HeapFree(v12, 0, v11);
      }
      *((_QWORD *)a3 + 10) = v9;
    }
    else
    {
      v6 = -2147024882;
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Provider::GetPublisherCertificateDigest", 465, -2147024882);
    }
  }
  else
  {
    v6 = -2147024809;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "Provider::GetPublisherCertificateDigest", 461, -2147024809);
  }
LABEL_17:
  if ( ppvData )
    SafeArrayUnaccessData(psa);
  if ( psa )
    SafeArrayDestroy(psa);
  return v6;
}

```

## disassembly

```asm
0x1400399e8  mov     r11, rsp
0x1400399eb  mov     [r11+18h], rbx
0x1400399ef  mov     [r11+8], rcx
0x1400399f3  push    rbp
0x1400399f4  push    rsi
0x1400399f5  push    rdi
0x1400399f6  sub     rsp, 30h
0x1400399fa  mov     rax, [rdx]
0x1400399fd  mov     rcx, rdx
0x140039a00  lea     rdx, [r11+8]
0x140039a04  mov     qword ptr [r11+8], 0
0x140039a0c  mov     rbp, r8
0x140039a0f  mov     qword ptr [r11+10h], 0
0x140039a17  mov     rax, [rax+60h]
0x140039a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039a20  mov     ebx, eax
0x140039a22  test    eax, eax
0x140039a24  jns     short loc_140039A4D
0x140039a26  mov     r9d, 1BCh
0x140039a2c  mov     [rsp+48h+var_28], eax
0x140039a30  lea     r8, aProviderGetpub; "Provider::GetPublisherCertificateDigest"
0x140039a37  mov     ecx, 1; Level
0x140039a3c  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140039a43  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140039a48  jmp     loc_140039B16
0x140039a4d  mov     rcx, [rsp+48h+psa]; psa
0x140039a52  test    rcx, rcx
0x140039a55  jz      loc_140039B16
0x140039a5b  lea     rdx, [rsp+48h+ppvData]; ppvData
0x140039a60  call    cs:__imp_SafeArrayAccessData
0x140039a67  nop     dword ptr [rax+rax+00h]
0x140039a6c  mov     ebx, eax
0x140039a6e  test    eax, eax
0x140039a70  jns     short loc_140039A7A
0x140039a72  mov     r9d, 1C0h
0x140039a78  jmp     short loc_140039A2C
0x140039a7a  mov     rax, [rsp+48h+psa]
0x140039a7f  cmp     dword ptr [rax+18h], 14h
0x140039a83  jz      short loc_140039A96
0x140039a85  mov     ebx, 80070057h
0x140039a8a  mov     r9d, 1CDh
0x140039a90  mov     [rsp+48h+var_28], ebx
0x140039a94  jmp     short loc_140039A30
0x140039a96  call    cs:__imp_GetProcessHeap
0x140039a9d  nop     dword ptr [rax+rax+00h]
0x140039aa2  xor     edx, edx; dwFlags
0x140039aa4  mov     rcx, rax; hHeap
0x140039aa7  lea     r8d, [rdx+14h]; dwBytes
0x140039aab  call    cs:__imp_HeapAlloc
0x140039ab2  nop     dword ptr [rax+rax+00h]
0x140039ab7  mov     rdi, rax
0x140039aba  test    rax, rax
0x140039abd  jnz     short loc_140039AD3
0x140039abf  mov     ebx, 8007000Eh
0x140039ac4  mov     r9d, 1D1h
0x140039aca  mov     [rsp+48h+var_28], ebx
0x140039ace  jmp     loc_140039A30
0x140039ad3  xor     edx, edx
0x140039ad5  mov     rax, [rsp+48h+ppvData]
0x140039ada  mov     cl, [rdx+rax]
0x140039add  mov     [rdi+rdx], cl
0x140039ae0  inc     rdx
0x140039ae3  cmp     rdx, 14h
0x140039ae7  jnz     short loc_140039AD5
0x140039ae9  mov     rsi, [rbp+50h]
0x140039aed  test    rsi, rsi
0x140039af0  jz      short loc_140039B12
0x140039af2  call    cs:__imp_GetProcessHeap
0x140039af9  nop     dword ptr [rax+rax+00h]
0x140039afe  mov     r8, rsi; lpMem
0x140039b01  xor     edx, edx; dwFlags
0x140039b03  mov     rcx, rax; hHeap
0x140039b06  call    cs:__imp_HeapFree
0x140039b0d  nop     dword ptr [rax+rax+00h]
0x140039b12  mov     [rbp+50h], rdi
0x140039b16  cmp     [rsp+48h+ppvData], 0
0x140039b1c  jz      short loc_140039B2F
0x140039b1e  mov     rcx, [rsp+48h+psa]; psa
0x140039b23  call    cs:__imp_SafeArrayUnaccessData
0x140039b2a  nop     dword ptr [rax+rax+00h]
0x140039b2f  mov     rcx, [rsp+48h+psa]; psa
0x140039b34  test    rcx, rcx
0x140039b37  jz      short loc_140039B45
0x140039b39  call    cs:__imp_SafeArrayDestroy
0x140039b40  nop     dword ptr [rax+rax+00h]
0x140039b45  mov     eax, ebx
0x140039b47  mov     rbx, [rsp+48h+arg_10]
0x140039b4c  add     rsp, 30h
0x140039b50  pop     rdi
0x140039b51  pop     rsi
0x140039b52  pop     rbp
0x140039b53  retn
```
