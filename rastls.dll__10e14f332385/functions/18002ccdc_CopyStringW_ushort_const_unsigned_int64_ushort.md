# CopyStringW(ushort const *,unsigned __int64,ushort * *)

- ea: `0x18002ccdc`
- end: `0x18002ce06`
- name: `?CopyStringW@@YAJPEBG_KPEAPEAG@Z`
- size: `298`
- prototype: `__int64 __fastcall(const unsigned __int16 *Source, unsigned __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180079000`

## callees

- `0x18002c90c`
- `0x18002ccdc`
- `0x18002ce0c`
- `0x180035664`
- `0x180036218`
- `0x18003779c`
- `0x18007885c`

## string_xrefs

- `0x18002cd02`: `CopyStringW`
- `0x18002cd1c`: `CopyStringW`
- `0x18002cd41`: `CopyStringW`
- `0x18002cd8b`: `CopyStringW`
- `0x18002cdc2`: `CopyStringW`

## pseudocode

```c
__int64 __fastcall CopyStringW(const unsigned __int16 *Source, __int64 a2, unsigned __int16 **a3)
{
  unsigned __int16 *v3; // rdi
  signed int v7; // ebx
  const unsigned __int16 *v8; // rdx
  unsigned __int64 v9; // rax
  unsigned __int16 *v10; // rax
  rsize_t v11; // r14
  unsigned int v12; // eax

  v3 = 0;
  if ( !a3 )
  {
    v7 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringW", L"pDest");
    v8 = L"pDest";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringW", v8);
    goto LABEL_14;
  }
  *a3 = 0;
  if ( !Source )
  {
    v7 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringW", L"source");
    v8 = L"source";
    goto LABEL_3;
  }
  v9 = 2 * (a2 + 1);
  if ( !is_mul_ok(a2 + 1, 2u) )
    v9 = -1;
  v10 = (unsigned __int16 *)operator new[](v9, (const struct std::nothrow_t *)std::nothrow);
  v3 = v10;
  if ( v10 )
  {
    v11 = 2 * a2;
    v12 = memcpy_s_2(v10, v11, Source, v11);
    v7 = v12;
    if ( v12 )
    {
      Logger::TraceError(L"%s: wmemcpy_s failed with error code: 0x%08x.", L"CopyStringW", v12);
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
    }
    else
    {
      *a3 = v3;
      v7 = 0;
      v3[v11 / 2] = 0;
      v3 = 0;
    }
  }
  else
  {
    v7 = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"CopyStringW");
  }
LABEL_14:
  operator delete(v3);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002ccdc  push    rbx
0x18002ccde  push    rsi
0x18002ccdf  push    rdi
0x18002cce0  push    r14
0x18002cce2  sub     rsp, 28h
0x18002cce6  xor     edi, edi
0x18002cce8  mov     rsi, r8
0x18002cceb  mov     r14, rdx
0x18002ccee  mov     rbx, rcx
0x18002ccf1  test    r8, r8
0x18002ccf4  jnz     short loc_18002CD2D
0x18002ccf6  lea     r8, aPdest; "pDest"
0x18002ccfd  mov     ebx, 80070057h
0x18002cd02  lea     rdx, aCopystringw; "CopyStringW"
0x18002cd09  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18002cd10  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002cd15  lea     rdx, aPdest; "pDest"
0x18002cd1c  lea     rcx, aCopystringw; "CopyStringW"
0x18002cd23  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18002cd28  jmp     loc_18002CDF2
0x18002cd2d  mov     [r8], rdi
0x18002cd30  test    rbx, rbx
0x18002cd33  jnz     short loc_18002CD5D
0x18002cd35  lea     r8, aSource; "source"
0x18002cd3c  mov     ebx, 80070057h
0x18002cd41  lea     rdx, aCopystringw; "CopyStringW"
0x18002cd48  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18002cd4f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002cd54  lea     rdx, aSource; "source"
0x18002cd5b  jmp     short loc_18002CD1C
0x18002cd5d  lea     rcx, [rdx+1]
0x18002cd61  mov     eax, 2
0x18002cd66  mul     rcx
0x18002cd69  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002cd70  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002cd77  cmovb   rax, rcx
0x18002cd7b  mov     rcx, rax; unsigned __int64
0x18002cd7e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002cd83  mov     rdi, rax
0x18002cd86  test    rax, rax
0x18002cd89  jnz     short loc_18002CDA5
0x18002cd8b  lea     rdx, aCopystringw; "CopyStringW"
0x18002cd92  mov     ebx, 8007000Eh
0x18002cd97  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x18002cd9e  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18002cda3  jmp     short loc_18002CDF2
0x18002cda5  add     r14, r14
0x18002cda8  mov     r8, rbx; Source
0x18002cdab  mov     r9, r14; SourceSize
0x18002cdae  mov     rdx, r14; DestinationSize
0x18002cdb1  mov     rcx, rdi; Destination
0x18002cdb4  call    memcpy_s_2
0x18002cdb9  mov     ebx, eax
0x18002cdbb  test    eax, eax
0x18002cdbd  jz      short loc_18002CDE4
0x18002cdbf  mov     r8d, eax
0x18002cdc2  lea     rdx, aCopystringw; "CopyStringW"
0x18002cdc9  lea     rcx, aSWmemcpySFaile; "%s: wmemcpy_s failed with error code: 0"...
0x18002cdd0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002cdd5  test    ebx, ebx
0x18002cdd7  jle     short loc_18002CDF2
0x18002cdd9  movzx   ebx, bx
0x18002cddc  or      ebx, 80070000h
0x18002cde2  jmp     short loc_18002CDF2
0x18002cde4  xor     ecx, ecx
0x18002cde6  mov     [rsi], rdi
0x18002cde9  xor     ebx, ebx
0x18002cdeb  mov     [r14+rdi], cx
0x18002cdf0  xor     edi, edi
0x18002cdf2  mov     rcx, rdi; Block
0x18002cdf5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002cdfa  mov     eax, ebx
0x18002cdfc  add     rsp, 28h
0x18002ce00  pop     r14
0x18002ce02  pop     rdi
0x18002ce03  pop     rsi
0x18002ce04  pop     rbx
0x18002ce05  retn
```
