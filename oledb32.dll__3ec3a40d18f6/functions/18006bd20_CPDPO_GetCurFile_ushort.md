# CPDPO::GetCurFile(ushort * *)

- ea: `0x18006bd20`
- end: `0x18006bdfd`
- name: `?GetCurFile@CPDPO@@UEAAJPEAPEAG@Z`
- size: `221`
- prototype: `__int64 __fastcall(CPDPO *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x1800112b0`
- `0x180013870`
- `0x180029560`
- `0x18006bd20`
- `0x18007e6d6`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18006bd38`
- `KERNEL32!EnterCriticalSection` at `0x18006bd38`
- `KERNEL32!LeaveCriticalSection` at `0x18006bdc4`
- `KERNEL32!LeaveCriticalSection` at `0x18006bdc4`
- `ole32!CoTaskMemAlloc` at `0x18006bd59`
- `ole32!CoTaskMemAlloc` at `0x18006bd59`

## pseudocode

```c
__int64 __fastcall CPDPO::GetCurFile(CPDPO *this, unsigned __int16 **a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  __int64 v5; // rax
  unsigned __int64 v6; // rdi
  unsigned __int16 *v7; // rax
  unsigned int v8; // ebx
  __int64 v9; // rdx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(*((_QWORD *)this + 12) + 2 * v5) );
  v6 = v5 + 1;
  v7 = (unsigned __int16 *)CoTaskMemAlloc(2 * (v5 + 1));
  *a2 = v7;
  if ( v7 )
  {
    StringCchCopyW(v7, v6, *((const unsigned __int16 **)this + 12));
    v8 = wcscmp_0(*((const wchar_t **)this + 12), L"*.udl") == 0;
    LeaveCriticalSection(v2);
    if ( (bidGblFlags & 2) != 0 )
    {
      v9 = 265225;
      return (unsigned int)bidTraceHR(off_1800C8470[0], v9, L"<CPDPO::GetCurFile|Trace|HR> ", v8);
    }
  }
  else
  {
    v8 = -2147024882;
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147024882, L"<CPDPO::GetCurFile|OLEDB|ERR> ", 0xF1u);
      if ( (bidGblFlags & 2) != 0 )
      {
        v9 = 246793;
        return (unsigned int)bidTraceHR(off_1800C8470[0], v9, L"<CPDPO::GetCurFile|Trace|HR> ", v8);
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18006bd20  push    rbx
0x18006bd22  push    rbp
0x18006bd23  push    rsi
0x18006bd24  push    rdi
0x18006bd25  push    r14
0x18006bd27  sub     rsp, 20h
0x18006bd2b  lea     rsi, [rcx+20h]
0x18006bd2f  mov     rbx, rcx
0x18006bd32  mov     rcx, rsi; lpCriticalSection
0x18006bd35  mov     r14, rdx
0x18006bd38  call    cs:__imp_EnterCriticalSection
0x18006bd3e  mov     rcx, [rbx+60h]
0x18006bd42  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006bd46  xor     ebp, ebp
0x18006bd48  inc     rax
0x18006bd4b  cmp     [rcx+rax*2], bp
0x18006bd4f  jnz     short loc_18006BD48
0x18006bd51  lea     rdi, [rax+1]
0x18006bd55  lea     rcx, [rdi+rdi]; cb
0x18006bd59  call    cs:__imp_CoTaskMemAlloc
0x18006bd5f  mov     [r14], rax
0x18006bd62  test    rax, rax
0x18006bd65  jnz     short loc_18006BD9B
0x18006bd67  mov     eax, cs:_bidGblFlags
0x18006bd6d  mov     ebx, 8007000Eh
0x18006bd72  test    al, 2
0x18006bd74  jz      short loc_18006BDF0
0x18006bd76  mov     r8d, 0F1h; unsigned int
0x18006bd7c  lea     rdx, aCpdpoGetcurfil; "<CPDPO::GetCurFile|OLEDB|ERR> "
0x18006bd83  mov     ecx, ebx; int
0x18006bd85  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006bd8a  mov     eax, cs:_bidGblFlags
0x18006bd90  test    al, 2
0x18006bd92  jz      short loc_18006BDF0
0x18006bd94  mov     edx, 3C409h
0x18006bd99  jmp     short loc_18006BDD8
0x18006bd9b  mov     r8, [rbx+60h]; unsigned __int16 *
0x18006bd9f  mov     rdx, rdi; unsigned __int64
0x18006bda2  mov     rcx, rax; unsigned __int16 *
0x18006bda5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006bdaa  mov     rcx, [rbx+60h]; String1
0x18006bdae  lea     rdx, aUdl_0; "*.udl"
0x18006bdb5  call    wcscmp_0
0x18006bdba  test    eax, eax
0x18006bdbc  mov     ebx, ebp
0x18006bdbe  mov     rcx, rsi; lpCriticalSection
0x18006bdc1  setz    bl
0x18006bdc4  call    cs:__imp_LeaveCriticalSection
0x18006bdca  test    byte ptr cs:_bidGblFlags, 2
0x18006bdd1  jz      short loc_18006BDF0
0x18006bdd3  mov     edx, 40C09h
0x18006bdd8  mov     rcx, cs:off_1800C8470; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18006bddf  lea     r8, aCpdpoGetcurfil_0; "<CPDPO::GetCurFile|Trace|HR> "
0x18006bde6  mov     r9d, ebx
0x18006bde9  call    _bidTraceHR
0x18006bdee  mov     ebx, eax
0x18006bdf0  mov     eax, ebx
0x18006bdf2  add     rsp, 20h
0x18006bdf6  pop     r14
0x18006bdf8  pop     rdi
0x18006bdf9  pop     rsi
0x18006bdfa  pop     rbp
0x18006bdfb  pop     rbx
0x18006bdfc  retn
```
