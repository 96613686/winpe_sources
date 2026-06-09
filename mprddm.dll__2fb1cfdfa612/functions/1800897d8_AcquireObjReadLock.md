# AcquireObjReadLock

- ea: `0x1800897d8`
- end: `0x18008991d`
- name: `AcquireObjReadLock`
- size: `325`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180087070`
- `0x180088e64`

## callees

- `0x180071cec`
- `0x1800897d8`
- `0x18008a630`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180089834`
- `KERNEL32!LeaveCriticalSection` at `0x180089873`
- `KERNEL32!LeaveCriticalSection` at `0x180089834`
- `KERNEL32!LeaveCriticalSection` at `0x180089873`
- `KERNEL32!EnterCriticalSection` at `0x180089821`
- `KERNEL32!EnterCriticalSection` at `0x180089867`
- `KERNEL32!EnterCriticalSection` at `0x180089821`
- `KERNEL32!EnterCriticalSection` at `0x180089867`
- `rtutils!TracePrintfA` at `0x1800898e1`
- `rtutils!TracePrintfA` at `0x1800898e1`

## string_xrefs

- `0x1800898da`: `AcquireObjReadLock: Bad handle (0x%x)`
- `0x180089892`: `AcquireObjReadLock: Bad handle (0x%x)`

## pseudocode

```c
__int64 __fastcall AcquireObjReadLock(unsigned int a1)
{
  unsigned int v2; // edi
  char *v3; // rbx
  int v5; // [rsp+20h] [rbp-818h] BYREF
  _BYTE v6[2044]; // [rsp+24h] [rbp-814h] BYREF

  v2 = a1 >> 1;
  v5 = 0;
  memset_0(v6, 0, sizeof(v6));
  EnterCriticalSection(&stru_1800C9800);
  ++dword_1800C9830;
  LeaveCriticalSection(&stru_1800C9800);
  if ( (unsigned __int16)v2 < (unsigned int)dword_1800C983C
    && (v3 = (char *)qword_1800C9848 + 72 * (unsigned __int16)v2, HIWORD(v2) == *((_WORD *)v3 + 32))
    && *((_QWORD *)v3 + 7) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)qword_1800C9848 + 72 * (unsigned __int16)v2));
    ++*((_DWORD *)v3 + 12);
    LeaveCriticalSection((LPCRITICAL_SECTION)v3);
    return 0;
  }
  else
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        LOWORD(v5) = 0;
        FormatRRASErrorString(&v5, L"AcquireObjReadLock: Bad handle (0x%x)", a1);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v5);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "AcquireObjReadLock: Bad handle (0x%x)", a1);
    }
    ReleaseReadLock(&stru_1800C9800);
    return 6;
  }
}

```

## disassembly

```asm
0x1800897d8  mov     [rsp+arg_8], rbx
0x1800897dd  mov     [rsp+arg_10], rsi
0x1800897e2  push    rdi
0x1800897e3  sub     rsp, 830h
0x1800897ea  mov     rax, cs:__security_cookie
0x1800897f1  xor     rax, rsp
0x1800897f4  mov     [rsp+838h+var_18], rax
0x1800897fc  mov     edi, ecx
0x1800897fe  mov     esi, ecx
0x180089800  xor     eax, eax
0x180089802  shr     edi, 1
0x180089804  lea     rcx, [rsp+838h+var_814]; void *
0x180089809  mov     [rsp+838h+var_818], eax
0x18008980d  xor     edx, edx; Val
0x18008980f  mov     r8d, 7FCh; Size
0x180089815  call    memset_0
0x18008981a  lea     rcx, stru_1800C9800; lpCriticalSection
0x180089821  call    cs:__imp_EnterCriticalSection
0x180089827  inc     cs:dword_1800C9830
0x18008982d  lea     rcx, stru_1800C9800; lpCriticalSection
0x180089834  call    cs:__imp_LeaveCriticalSection
0x18008983a  movzx   eax, di
0x18008983d  cmp     eax, cs:dword_1800C983C
0x180089843  jnb     short loc_18008987D
0x180089845  lea     rcx, [rax+rax*8]
0x180089849  shr     edi, 10h
0x18008984c  mov     rax, cs:qword_1800C9848
0x180089853  lea     rbx, [rax+rcx*8]
0x180089857  cmp     di, [rbx+40h]
0x18008985b  jnz     short loc_18008987D
0x18008985d  cmp     qword ptr [rbx+38h], 0
0x180089862  jz      short loc_18008987D
0x180089864  mov     rcx, rbx; lpCriticalSection
0x180089867  call    cs:__imp_EnterCriticalSection
0x18008986d  inc     dword ptr [rbx+30h]
0x180089870  mov     rcx, rbx; lpCriticalSection
0x180089873  call    cs:__imp_LeaveCriticalSection
0x180089879  xor     eax, eax
0x18008987b  jmp     short loc_1800898F8
0x18008987d  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180089884  jz      short loc_1800898CC
0x180089886  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x18008988e  jz      short loc_1800898E7
0x180089890  xor     eax, eax
0x180089892  lea     rdx, aAcquireobjread; "AcquireObjReadLock: Bad handle (0x%x)"
0x180089899  mov     r8d, esi
0x18008989c  mov     word ptr [rsp+838h+var_818], ax
0x1800898a1  lea     rcx, [rsp+838h+var_818]
0x1800898a6  call    FormatRRASErrorString
0x1800898ab  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x1800898b2  lea     r8, [rsp+838h+var_818]
0x1800898b7  mov     rcx, cs:gNdpspEtwContext
0x1800898be  mov     rax, cs:gNdpspTemplateFunc
0x1800898c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800898ca  jmp     short loc_1800898E7
0x1800898cc  mov     ecx, cs:dwTraceId; dwTraceID
0x1800898d2  cmp     ecx, 0FFFFFFFFh
0x1800898d5  jz      short loc_1800898E7
0x1800898d7  mov     r8d, esi
0x1800898da  lea     rdx, aAcquireobjread_0; "AcquireObjReadLock: Bad handle (0x%x)"
0x1800898e1  call    cs:__imp_TracePrintfA
0x1800898e7  lea     rcx, stru_1800C9800
0x1800898ee  call    ReleaseReadLock
0x1800898f3  mov     eax, 6
0x1800898f8  mov     rcx, [rsp+838h+var_18]
0x180089900  xor     rcx, rsp; StackCookie
0x180089903  call    __security_check_cookie
0x180089908  lea     r11, [rsp+838h+var_8]
0x180089910  mov     rbx, [r11+18h]
0x180089914  mov     rsi, [r11+20h]
0x180089918  mov     rsp, r11
0x18008991b  pop     rdi
0x18008991c  retn
```
