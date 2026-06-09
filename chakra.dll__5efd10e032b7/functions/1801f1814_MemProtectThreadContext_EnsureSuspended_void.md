# MemProtectThreadContext::EnsureSuspended(void)

- ea: `0x1801f1814`
- end: `0x1801f192b`
- name: `?EnsureSuspended@MemProtectThreadContext@@QEAAXXZ`
- size: `279`
- prototype: `void __fastcall(MemProtectThreadContext *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1801f131c`

## callees

- `0x1801f14b0`
- `0x1801f1814`
- `0x1801f1934`
- `0x1801f1a0c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x1801f1907`
- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x1801f1907`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801f1836`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801f188d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801f1836`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801f188d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801f18d8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801f18d8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1801f18af`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1801f18af`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x1801f1859`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x1801f1859`

## pseudocode

```c
void __fastcall MemProtectThreadContext::EnsureSuspended(MemProtectThreadContext *this)
{
  ULONGLONG TickCount64; // r14
  unsigned int v3; // esi
  void *v4; // rcx
  char v5; // bp
  unsigned __int64 v6; // rdi

  if ( !MemProtectThreadContext::IsLeakedThread(this) )
  {
    TickCount64 = GetTickCount64();
    v3 = 0;
    while ( 1 )
    {
      v4 = (void *)*((_QWORD *)this + 11);
      *((_DWORD *)this + 40) = 1048579;
      if ( GetThreadContext(v4, (LPCONTEXT)((char *)this + 112)) )
      {
        if ( !*((_BYTE *)this + 16) )
          return;
      }
      else if ( MemProtectThreadContext::IsLeakedThread(this) )
      {
        return;
      }
      v5 = 0;
      do
      {
        v6 = GetTickCount64() - TickCount64;
        if ( v6 > 0x3E8 )
          RaiseFailFastException(0, 0, 0);
        if ( !v5 )
        {
          MemProtectThreadContext::ResumeFromSuspension(this);
          v5 = 1;
        }
        ++v3;
        if ( v6 <= 0xA )
        {
          if ( (unsigned int)dword_18073F484 <= 1 || v3 == 20 * (v3 / 0x14) )
            SwitchToThread();
          else
            _mm_pause();
        }
        else
        {
          Sleep(1u);
        }
      }
      while ( *((_BYTE *)this + 16) );
      MemProtectThreadContext::RequestSuspension(this);
    }
  }
}

```

## disassembly

```asm
0x1801f1814  mov     [rsp+arg_0], rcx
0x1801f1819  push    rbx
0x1801f181a  push    rbp
0x1801f181b  push    rsi
0x1801f181c  push    rdi
0x1801f181d  push    r14
0x1801f181f  push    r15
0x1801f1821  sub     rsp, 28h
0x1801f1825  mov     rbx, [rsp+58h+arg_0]
0x1801f182a  mov     rcx, rbx; this
0x1801f182d  call    ?IsLeakedThread@MemProtectThreadContext@@QEAA_NXZ; MemProtectThreadContext::IsLeakedThread(void)
0x1801f1832  test    al, al
0x1801f1834  jnz     short loc_1801F1870
0x1801f1836  call    cs:__imp_GetTickCount64
0x1801f183d  nop     dword ptr [rax+rax+00h]
0x1801f1842  mov     r14, rax
0x1801f1845  xor     esi, esi
0x1801f1847  mov     rcx, [rbx+58h]; hThread
0x1801f184b  lea     rdx, [rbx+70h]; lpContext
0x1801f184f  mov     dword ptr [rbx+0A0h], 100003h
0x1801f1859  call    cs:__imp_GetThreadContext
0x1801f1860  nop     dword ptr [rax+rax+00h]
0x1801f1865  test    eax, eax
0x1801f1867  jz      short loc_1801F187E
0x1801f1869  mov     al, [rbx+10h]
0x1801f186c  test    al, al
0x1801f186e  jnz     short loc_1801F188A
0x1801f1870  add     rsp, 28h
0x1801f1874  pop     r15
0x1801f1876  pop     r14
0x1801f1878  pop     rdi
0x1801f1879  pop     rsi
0x1801f187a  pop     rbp
0x1801f187b  pop     rbx
0x1801f187c  retn
0x1801f187e  mov     rcx, rbx; this
0x1801f1881  call    ?IsLeakedThread@MemProtectThreadContext@@QEAA_NXZ; MemProtectThreadContext::IsLeakedThread(void)
0x1801f1886  test    al, al
0x1801f1888  jnz     short loc_1801F1870
0x1801f188a  xor     bpl, bpl
0x1801f188d  call    cs:__imp_GetTickCount64
0x1801f1894  nop     dword ptr [rax+rax+00h]
0x1801f1899  mov     rdi, rax
0x1801f189c  sub     rdi, r14
0x1801f189f  cmp     rdi, 3E8h
0x1801f18a6  jbe     short loc_1801F18BB
0x1801f18a8  xor     r8d, r8d; dwFlags
0x1801f18ab  xor     edx, edx; pContextRecord
0x1801f18ad  xor     ecx, ecx; pExceptionRecord
0x1801f18af  call    cs:__imp_RaiseFailFastException
0x1801f18b6  nop     dword ptr [rax+rax+00h]
0x1801f18bb  test    bpl, bpl
0x1801f18be  jnz     short loc_1801F18CB
0x1801f18c0  mov     rcx, rbx; this
0x1801f18c3  call    ?ResumeFromSuspension@MemProtectThreadContext@@QEAAXXZ; MemProtectThreadContext::ResumeFromSuspension(void)
0x1801f18c8  mov     bpl, 1
0x1801f18cb  inc     esi
0x1801f18cd  cmp     rdi, 0Ah
0x1801f18d1  jbe     short loc_1801F18E6
0x1801f18d3  mov     ecx, 1; dwMilliseconds
0x1801f18d8  call    cs:__imp_Sleep
0x1801f18df  nop     dword ptr [rax+rax+00h]
0x1801f18e4  jmp     short loc_1801F1913
0x1801f18e6  cmp     cs:dword_18073F484, 1
0x1801f18ed  jbe     short loc_1801F1907
0x1801f18ef  mov     eax, 0CCCCCCCDh
0x1801f18f4  mul     esi
0x1801f18f6  shr     edx, 4
0x1801f18f9  lea     ecx, [rdx+rdx*4]
0x1801f18fc  shl     ecx, 2
0x1801f18ff  cmp     esi, ecx
0x1801f1901  jz      short loc_1801F1907
0x1801f1903  pause
0x1801f1905  jmp     short loc_1801F1913
0x1801f1907  call    cs:__imp_SwitchToThread
0x1801f190e  nop     dword ptr [rax+rax+00h]
0x1801f1913  mov     al, [rbx+10h]
0x1801f1916  test    al, al
0x1801f1918  jnz     loc_1801F188D
0x1801f191e  mov     rcx, rbx; this
0x1801f1921  call    ?RequestSuspension@MemProtectThreadContext@@QEAAXXZ; MemProtectThreadContext::RequestSuspension(void)
0x1801f1926  jmp     loc_1801F1847
```
