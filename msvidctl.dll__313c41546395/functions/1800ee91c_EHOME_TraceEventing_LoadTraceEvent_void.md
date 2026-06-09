# EHOME_TraceEventing::LoadTraceEvent(void)

- ea: `0x1800ee91c`
- end: `0x1800eeb35`
- name: `?LoadTraceEvent@EHOME_TraceEventing@@QEAAXXZ`
- size: `537`
- prototype: `void __fastcall(EHOME_TraceEventing *__hidden this)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x1800b98f0`
- `0x1800b9ca8`
- `0x1800eeb3c`
- `0x1800eeb8c`

## callees

- `0x180004640`
- `0x180004740`
- `0x180004b54`
- `0x1800054bc`
- `0x1800ee91c`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x1800ee9a6`
- `KERNEL32!LoadLibraryW` at `0x1800ee9a6`
- `KERNEL32!FreeLibrary` at `0x1800eeade`
- `KERNEL32!FreeLibrary` at `0x1800eeb07`
- `KERNEL32!FreeLibrary` at `0x1800eeade`
- `KERNEL32!FreeLibrary` at `0x1800eeb07`
- `KERNEL32!GetProcAddress` at `0x1800ee9d4`
- `KERNEL32!GetProcAddress` at `0x1800ee9e8`
- `KERNEL32!GetProcAddress` at `0x1800ee9fd`
- `KERNEL32!GetProcAddress` at `0x1800eea12`
- `KERNEL32!GetProcAddress` at `0x1800eea27`
- `KERNEL32!GetProcAddress` at `0x1800eea3c`
- `KERNEL32!GetProcAddress` at `0x1800eea51`
- `KERNEL32!GetProcAddress` at `0x1800eea66`
- `KERNEL32!GetProcAddress` at `0x1800eea7b`
- `KERNEL32!GetProcAddress` at `0x1800ee9d4`
- `KERNEL32!GetProcAddress` at `0x1800ee9e8`
- `KERNEL32!GetProcAddress` at `0x1800ee9fd`
- `KERNEL32!GetProcAddress` at `0x1800eea12`
- `KERNEL32!GetProcAddress` at `0x1800eea27`
- `KERNEL32!GetProcAddress` at `0x1800eea3c`
- `KERNEL32!GetProcAddress` at `0x1800eea51`
- `KERNEL32!GetProcAddress` at `0x1800eea66`
- `KERNEL32!GetProcAddress` at `0x1800eea7b`
- `KERNEL32!LeaveCriticalSection` at `0x1800ee966`
- `KERNEL32!LeaveCriticalSection` at `0x1800ee971`
- `KERNEL32!LeaveCriticalSection` at `0x1800ee966`
- `KERNEL32!LeaveCriticalSection` at `0x1800ee971`
- `KERNEL32!EnterCriticalSection` at `0x1800ee957`
- `KERNEL32!EnterCriticalSection` at `0x1800eeac4`
- `KERNEL32!EnterCriticalSection` at `0x1800ee957`
- `KERNEL32!EnterCriticalSection` at `0x1800eeac4`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800ee99b`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800ee99b`

## string_xrefs

- `0x1800ee994`: `%SystemRoot%\ehome\ehTrace.dll`

## pseudocode

```c
void __fastcall EHOME_TraceEventing::LoadTraceEvent(EHOME_TraceEventing *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  struct _RTL_CRITICAL_SECTION *v3; // rcx
  HMODULE LibraryW; // rbp
  FARPROC *v5; // rbx
  FARPROC ProcAddress; // rax
  bool v7; // zf
  WCHAR Dst[128]; // [rsp+20h] [rbp-128h] BYREF

  if ( *((_BYTE *)this + 64) )
  {
    v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    v3 = v2;
    if ( *((_BYTE *)this + 8) )
    {
LABEL_3:
      LeaveCriticalSection(v3);
      return;
    }
    LeaveCriticalSection(v2);
    memset_0(Dst, 0, sizeof(Dst));
    ExpandEnvironmentStringsW(L"%SystemRoot%\\ehome\\ehTrace.dll", Dst, 0x80u);
    LibraryW = LoadLibraryW(Dst);
    if ( LibraryW )
    {
      v5 = (FARPROC *)operator new(0x48u);
      *v5 = GetProcAddress(*((HMODULE *)this + 2), "ehRegisterTraceGUIDs");
      v5[1] = GetProcAddress(*((HMODULE *)this + 2), "ehRegisterCounterGUID");
      v5[2] = GetProcAddress(*((HMODULE *)this + 2), "ehUnregisterTraceGUIDs");
      v5[3] = GetProcAddress(*((HMODULE *)this + 2), "ehUnregisterCounterGUIDs");
      v5[4] = GetProcAddress(*((HMODULE *)this + 2), "ehAllocateEventBuffer");
      v5[5] = GetProcAddress(*((HMODULE *)this + 2), "ehFreeEventBuffer");
      v5[6] = GetProcAddress(*((HMODULE *)this + 2), "ehIsTraceEnabled");
      v5[7] = GetProcAddress(*((HMODULE *)this + 2), "ehTraceCounter");
      ProcAddress = GetProcAddress(*((HMODULE *)this + 2), "ehTraceEvent");
      v7 = *v5 == 0;
      v5[8] = ProcAddress;
      if ( !v7 && v5[1] && v5[2] && v5[3] && v5[4] && v5[5] && v5[6] && v5[7] && ProcAddress )
      {
        EnterCriticalSection(v2);
        if ( *((_BYTE *)this + 8) )
        {
          operator delete(v5, 0x48u);
          FreeLibrary(LibraryW);
        }
        else
        {
          *(_QWORD *)this = v5;
          *((_QWORD *)this + 2) = LibraryW;
          *((_BYTE *)this + 8) = 1;
        }
        v3 = v2;
        goto LABEL_3;
      }
      operator delete(v5, 0x48u);
      FreeLibrary(LibraryW);
    }
  }
}

```

## disassembly

```asm
0x1800ee91c  mov     [rsp+arg_8], rbx
0x1800ee921  mov     [rsp+arg_10], rbp
0x1800ee926  push    rsi
0x1800ee927  push    rdi
0x1800ee928  push    r15
0x1800ee92a  sub     rsp, 130h
0x1800ee931  mov     rax, cs:__security_cookie
0x1800ee938  xor     rax, rsp
0x1800ee93b  mov     [rsp+148h+var_28], rax
0x1800ee943  cmp     byte ptr [rcx+40h], 0
0x1800ee947  mov     rdi, rcx
0x1800ee94a  jz      loc_1800EEB0D
0x1800ee950  lea     rsi, [rcx+18h]
0x1800ee954  mov     rcx, rsi; lpCriticalSection
0x1800ee957  call    cs:__imp_EnterCriticalSection
0x1800ee95d  cmp     byte ptr [rdi+8], 0
0x1800ee961  mov     rcx, rsi; lpCriticalSection
0x1800ee964  jz      short loc_1800EE971
0x1800ee966  call    cs:__imp_LeaveCriticalSection
0x1800ee96c  jmp     loc_1800EEB0D
0x1800ee971  call    cs:__imp_LeaveCriticalSection
0x1800ee977  xor     edx, edx; Val
0x1800ee979  lea     rcx, [rsp+148h+Dst]; void *
0x1800ee97e  mov     r8d, 100h; Size
0x1800ee984  call    memset_0
0x1800ee989  mov     r8d, 80h; nSize
0x1800ee98f  lea     rdx, [rsp+148h+Dst]; lpDst
0x1800ee994  lea     rcx, Src; "%SystemRoot%\\ehome\\ehTrace.dll"
0x1800ee99b  call    cs:__imp_ExpandEnvironmentStringsW
0x1800ee9a1  lea     rcx, [rsp+148h+Dst]; lpLibFileName
0x1800ee9a6  call    cs:__imp_LoadLibraryW
0x1800ee9ac  mov     rbp, rax
0x1800ee9af  test    rax, rax
0x1800ee9b2  jz      loc_1800EEB0D
0x1800ee9b8  mov     r15d, 48h ; 'H'
0x1800ee9be  mov     ecx, r15d; Size
0x1800ee9c1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ee9c6  mov     rcx, [rdi+10h]; hModule
0x1800ee9ca  lea     rdx, aEhregistertrac; "ehRegisterTraceGUIDs"
0x1800ee9d1  mov     rbx, rax
0x1800ee9d4  call    cs:__imp_GetProcAddress
0x1800ee9da  mov     [rbx], rax
0x1800ee9dd  lea     rdx, aEhregistercoun; "ehRegisterCounterGUID"
0x1800ee9e4  mov     rcx, [rdi+10h]; hModule
0x1800ee9e8  call    cs:__imp_GetProcAddress
0x1800ee9ee  mov     [rbx+8], rax
0x1800ee9f2  lea     rdx, aEhunregistertr; "ehUnregisterTraceGUIDs"
0x1800ee9f9  mov     rcx, [rdi+10h]; hModule
0x1800ee9fd  call    cs:__imp_GetProcAddress
0x1800eea03  mov     [rbx+10h], rax
0x1800eea07  lea     rdx, aEhunregisterco; "ehUnregisterCounterGUIDs"
0x1800eea0e  mov     rcx, [rdi+10h]; hModule
0x1800eea12  call    cs:__imp_GetProcAddress
0x1800eea18  mov     [rbx+18h], rax
0x1800eea1c  lea     rdx, aEhallocateeven; "ehAllocateEventBuffer"
0x1800eea23  mov     rcx, [rdi+10h]; hModule
0x1800eea27  call    cs:__imp_GetProcAddress
0x1800eea2d  mov     [rbx+20h], rax
0x1800eea31  lea     rdx, aEhfreeeventbuf; "ehFreeEventBuffer"
0x1800eea38  mov     rcx, [rdi+10h]; hModule
0x1800eea3c  call    cs:__imp_GetProcAddress
0x1800eea42  mov     [rbx+28h], rax
0x1800eea46  lea     rdx, aEhistraceenabl; "ehIsTraceEnabled"
0x1800eea4d  mov     rcx, [rdi+10h]; hModule
0x1800eea51  call    cs:__imp_GetProcAddress
0x1800eea57  mov     [rbx+30h], rax
0x1800eea5b  lea     rdx, aEhtracecounter; "ehTraceCounter"
0x1800eea62  mov     rcx, [rdi+10h]; hModule
0x1800eea66  call    cs:__imp_GetProcAddress
0x1800eea6c  mov     [rbx+38h], rax
0x1800eea70  lea     rdx, aEhtraceevent; "ehTraceEvent"
0x1800eea77  mov     rcx, [rdi+10h]; hModule
0x1800eea7b  call    cs:__imp_GetProcAddress
0x1800eea81  cmp     qword ptr [rbx], 0
0x1800eea85  mov     [rbx+40h], rax
0x1800eea89  jz      short loc_1800EEAF9
0x1800eea8b  cmp     qword ptr [rbx+8], 0
0x1800eea90  jz      short loc_1800EEAF9
0x1800eea92  cmp     qword ptr [rbx+10h], 0
0x1800eea97  jz      short loc_1800EEAF9
0x1800eea99  cmp     qword ptr [rbx+18h], 0
0x1800eea9e  jz      short loc_1800EEAF9
0x1800eeaa0  cmp     qword ptr [rbx+20h], 0
0x1800eeaa5  jz      short loc_1800EEAF9
0x1800eeaa7  cmp     qword ptr [rbx+28h], 0
0x1800eeaac  jz      short loc_1800EEAF9
0x1800eeaae  cmp     qword ptr [rbx+30h], 0
0x1800eeab3  jz      short loc_1800EEAF9
0x1800eeab5  cmp     qword ptr [rbx+38h], 0
0x1800eeaba  jz      short loc_1800EEAF9
0x1800eeabc  test    rax, rax
0x1800eeabf  jz      short loc_1800EEAF9
0x1800eeac1  mov     rcx, rsi; lpCriticalSection
0x1800eeac4  call    cs:__imp_EnterCriticalSection
0x1800eeaca  cmp     byte ptr [rdi+8], 0
0x1800eeace  jz      short loc_1800EEAEC
0x1800eead0  mov     edx, r15d; unsigned __int64
0x1800eead3  mov     rcx, rbx; void *
0x1800eead6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800eeadb  mov     rcx, rbp; hLibModule
0x1800eeade  call    cs:__imp_FreeLibrary
0x1800eeae4  mov     rcx, rsi
0x1800eeae7  jmp     loc_1800EE966
0x1800eeaec  mov     [rdi], rbx
0x1800eeaef  mov     [rdi+10h], rbp
0x1800eeaf3  mov     byte ptr [rdi+8], 1
0x1800eeaf7  jmp     short loc_1800EEAE4
0x1800eeaf9  mov     rdx, r15; unsigned __int64
0x1800eeafc  mov     rcx, rbx; void *
0x1800eeaff  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800eeb04  mov     rcx, rbp; hLibModule
0x1800eeb07  call    cs:__imp_FreeLibrary
0x1800eeb0d  mov     rcx, [rsp+148h+var_28]
0x1800eeb15  xor     rcx, rsp; StackCookie
0x1800eeb18  call    __security_check_cookie
0x1800eeb1d  lea     r11, [rsp+148h+var_18]
0x1800eeb25  mov     rbx, [r11+28h]
0x1800eeb29  mov     rbp, [r11+30h]
0x1800eeb2d  mov     rsp, r11
0x1800eeb30  pop     r15
0x1800eeb32  pop     rdi
0x1800eeb33  pop     rsi
0x1800eeb34  retn
```
