# DnsNbt_Cancel

- ea: `0x180023fc4`
- end: `0x18002419c`
- name: `DnsNbt_Cancel`
- size: `472`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180024680`
- `0x180047f4c`

## callees

- `0x180023fc4`
- `0x180024554`
- `0x1800249b8`
- `0x1800317e0`
- `0x1800dc9e0`
- `0x1800ddfa8`
- `0x1800e4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002412a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002412a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800240b1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800240b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023ff3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023ff3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002400c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002400c`
- `ntdll!NtCancelIoFile` at `0x18002406c`
- `ntdll!NtCancelIoFile` at `0x18002406c`

## string_xrefs

- `0x1800240a4`: `dnsapi.dll`

## pseudocode

```c
__int64 __fastcall DnsNbt_Cancel(char *lpMem)
{
  void *v1; // rdi
  int v3; // ebp
  unsigned int i; // esi
  __int64 v5; // rcx
  char *v6; // r9
  __int64 result; // rax
  HMODULE Library; // rax
  DWORD LastError; // eax
  void (__fastcall *v10)(void *, __int64, _QWORD, _QWORD); // rax

  v1 = 0;
  v3 = 0;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_q(1035, 27, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids, lpMem);
  AddRefNbtLookupContext(lpMem);
  EnterCriticalSection((LPCRITICAL_SECTION)(lpMem + 568));
  if ( *((_QWORD *)lpMem + 4) )
  {
    Library = LoadLibraryExW(L"dnsapi.dll", 0, 0x800u);
    *((_QWORD *)lpMem + 77) = Library;
    if ( Library )
    {
      v1 = (void *)*((_QWORD *)lpMem + 4);
      *((_QWORD *)lpMem + 4) = 0;
      v3 = 1;
    }
    else if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(1035, 28, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids, LastError);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(lpMem + 568));
  for ( i = 0; i < *((_DWORD *)lpMem + 2); ++i )
  {
    v5 = 1776LL * i;
    v6 = &lpMem[v5 + 624];
    if ( *(_QWORD *)v6 )
    {
      _m_prefetchw(v6 + 584);
      if ( (_InterlockedOr((volatile signed __int32 *)v6 + 146, 4u) & 7) == 1 )
      {
        NtCancelIoFile(*(HANDLE *)&lpMem[v5 + 624], (PIO_STATUS_BLOCK)(v6 + 536));
      }
      else if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      {
        WPP_SF_q(1035, 29, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids, v6);
      }
    }
  }
  if ( v1 )
  {
    v10 = (void (__fastcall *)(void *, __int64, _QWORD, _QWORD))*((_QWORD *)lpMem + 76);
    if ( v10 )
      v10(v1, 1223, 0, 0);
  }
  result = DeRefNbtLookupContext(lpMem);
  if ( v3 )
    return DeRefQueryBlobEx(v1);
  return result;
}

```

## disassembly

```asm
0x180023fc4  push    rbx
0x180023fc6  push    rbp
0x180023fc7  push    rsi
0x180023fc8  push    rdi
0x180023fc9  sub     rsp, 38h
0x180023fcd  xor     edi, edi
0x180023fcf  mov     rbx, rcx
0x180023fd2  xor     ebp, ebp
0x180023fd4  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180023fdb  jnz     loc_1800240FF
0x180023fe1  mov     rcx, rbx
0x180023fe4  call    AddRefNbtLookupContext
0x180023fe9  lea     rsi, [rbx+238h]
0x180023ff0  mov     rcx, rsi; lpCriticalSection
0x180023ff3  call    cs:__imp_EnterCriticalSection
0x180023ffa  nop     dword ptr [rax+rax+00h]
0x180023fff  cmp     [rbx+20h], rdi
0x180024003  jnz     loc_1800240A2
0x180024009  mov     rcx, rsi; lpCriticalSection
0x18002400c  call    cs:__imp_LeaveCriticalSection
0x180024013  nop     dword ptr [rax+rax+00h]
0x180024018  xor     esi, esi
0x18002401a  cmp     [rbx+8], esi
0x18002401d  jbe     short loc_18002407F
0x18002401f  mov     eax, esi
0x180024021  lea     r9, [rbx+270h]
0x180024028  imul    rcx, rax, 6F0h
0x18002402f  add     r9, rcx
0x180024032  cmp     qword ptr [r9], 0
0x180024036  jz      short loc_180024078
0x180024038  prefetchw byte ptr [r9+248h]
0x180024040  mov     eax, [r9+248h]
0x180024047  mov     edx, eax
0x180024049  or      edx, 4
0x18002404c  lock cmpxchg [r9+248h], edx
0x180024055  jnz     short loc_180024047
0x180024057  and     al, 7
0x180024059  cmp     al, 1
0x18002405b  jnz     short loc_1800240DB
0x18002405d  mov     rcx, [rcx+rbx+270h]; FileHandle
0x180024065  lea     rdx, [r9+218h]; IoStatusBlock
0x18002406c  call    cs:__imp_NtCancelIoFile
0x180024073  nop     dword ptr [rax+rax+00h]
0x180024078  inc     esi
0x18002407a  cmp     esi, [rbx+8]
0x18002407d  jb      short loc_18002401F
0x18002407f  test    rdi, rdi
0x180024082  jnz     loc_180024154
0x180024088  mov     rcx, rbx; lpMem
0x18002408b  call    DeRefNbtLookupContext
0x180024090  test    ebp, ebp
0x180024092  jnz     loc_18002417C
0x180024098  add     rsp, 38h
0x18002409c  pop     rdi
0x18002409d  pop     rsi
0x18002409e  pop     rbp
0x18002409f  pop     rbx
0x1800240a0  retn
0x1800240a2  xor     edx, edx; hFile
0x1800240a4  lea     rcx, LibFileName; "dnsapi.dll"
0x1800240ab  mov     r8d, 800h; dwFlags
0x1800240b1  call    cs:__imp_LoadLibraryExW
0x1800240b8  nop     dword ptr [rax+rax+00h]
0x1800240bd  mov     [rbx+268h], rax
0x1800240c4  test    rax, rax
0x1800240c7  jz      short loc_18002411D
0x1800240c9  mov     rdi, [rbx+20h]
0x1800240cd  mov     [rbx+20h], rbp
0x1800240d1  mov     ebp, 1
0x1800240d6  jmp     loc_180024009
0x1800240db  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800240e2  jz      short loc_180024078
0x1800240e4  mov     edx, 1Dh
0x1800240e9  lea     r8, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids
0x1800240f0  mov     ecx, 40Bh
0x1800240f5  call    WPP_SF_q
0x1800240fa  jmp     loc_180024078
0x1800240ff  mov     edx, 1Bh
0x180024104  lea     r8, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids
0x18002410b  mov     ecx, 40Bh
0x180024110  mov     r9, rbx
0x180024113  call    WPP_SF_q
0x180024118  jmp     loc_180023FE1
0x18002411d  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180024124  jz      loc_180024009
0x18002412a  call    cs:__imp_GetLastError
0x180024131  nop     dword ptr [rax+rax+00h]
0x180024136  mov     edx, 1Ch
0x18002413b  lea     r8, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids
0x180024142  mov     r9d, eax
0x180024145  mov     ecx, 40Bh
0x18002414a  call    WPP_SF_d
0x18002414f  jmp     loc_180024009
0x180024154  mov     rax, [rbx+260h]
0x18002415b  test    rax, rax
0x18002415e  jz      loc_180024088
0x180024164  xor     r9d, r9d
0x180024167  xor     r8d, r8d
0x18002416a  mov     edx, 4C7h
0x18002416f  mov     rcx, rdi
0x180024172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024177  jmp     loc_180024088
0x18002417c  mov     r9d, 11h
0x180024182  lea     rdx, aDnsnbtCancel; "DnsNbt_Cancel"
0x180024189  mov     r8d, 485h
0x18002418f  mov     rcx, rdi; lpMem
0x180024192  call    DeRefQueryBlobEx
0x180024197  jmp     loc_180024098
```
