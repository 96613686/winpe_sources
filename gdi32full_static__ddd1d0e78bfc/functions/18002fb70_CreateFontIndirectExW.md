# CreateFontIndirectExW

- ea: `0x18002fb70`
- end: `0x18002fd98`
- name: `CreateFontIndirectExW`
- size: `552`
- prototype: `HFONT __stdcall(const ENUMLOGFONTEXDVW *)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002ef90`
- `0x18002f680`
- `0x180079b10`
- `0x18008ab40`

## callees

- `0x18002fb70`
- `0x18002fda0`
- `0x18002feb0`
- `0x180041cb8`
- `0x180041d40`
- `0x18007f800`
- `0x180080604`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlRaiseException` at `0x18002fd3e`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlRaiseException` at `0x18002fd3e`
- `GDI32!GdiSetLastError` at `0x18002fcfd`
- `GDI32!GdiSetLastError` at `0x18002fcfd`
- `ntdll!RtlAllocateHeap` at `0x18002fc98`
- `ntdll!RtlAllocateHeap` at `0x18002fc98`
- `ntdll!RtlEnterCriticalSection` at `0x18002fba6`
- `ntdll!RtlEnterCriticalSection` at `0x18002fd6c`
- `ntdll!RtlEnterCriticalSection` at `0x18002fba6`
- `ntdll!RtlEnterCriticalSection` at `0x18002fd6c`
- `ntdll!RtlLeaveCriticalSection` at `0x18002fc11`
- `ntdll!RtlLeaveCriticalSection` at `0x18002fd87`
- `ntdll!RtlLeaveCriticalSection` at `0x18002fc11`
- `ntdll!RtlLeaveCriticalSection` at `0x18002fd87`
- `win32u!NtGdiHfontCreate` at `0x18002fc46`
- `win32u!NtGdiHfontCreate` at `0x18002fc46`

## string_xrefs

- `0x18002fd1d`: `plfCreateLOCALFONT`

## pseudocode

```c
HFONT __stdcall CreateFontIndirectExW(const ENUMLOGFONTEXDVW *a1)
{
  __int64 v1; // rsi
  _BOOL8 v3; // rbp
  unsigned __int64 v4; // rbx
  struct _LOCALFONT *v5; // rcx
  DWORD dvNumAxes; // edx
  _QWORD *Heap; // rax
  _QWORD *v9; // rbx
  __int64 v10; // r9
  __int64 v11; // r8
  _QWORD *v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rax
  _EXCEPTION_RECORD ExceptionRecord; // [rsp+30h] [rbp-D8h] BYREF

  v1 = 0;
  v3 = *(_QWORD *)&a1->elfEnumLogfontEx.elfLogFont.lfEscapement != 0;
  RtlEnterCriticalSection(&semLocal);
  v4 = (unsigned __int64)plfFreeListLOCALFONT;
  if ( !plfFreeListLOCALFONT )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x1E0u);
    v9 = Heap;
    if ( !Heap )
    {
      GdiSetLastError(8);
LABEL_17:
      v4 = 0;
      goto LABEL_7;
    }
    v10 = 1;
    Heap[3] = 0;
    Heap[5] = Heap;
    Heap[4] = 0;
    v11 = 6;
    do
    {
      v12 = &v9[v11];
      ++v10;
      v12[4] = 0;
      v13 = (__int64)&v9[v11 - 6];
      v14 = v13 ^ (unsigned __int64)&v9[v11];
      v12[3] = v13;
      v11 += 6;
      v12[5] = v14;
    }
    while ( v10 != 10 );
    v4 = (unsigned __int64)(v9 + 54);
  }
  plfFreeListLOCALFONT = *(struct _LOCALFONT **)(v4 + 24);
  v5 = plfFreeListLOCALFONT;
  plfFreeListLOCALFONTCopy = plfFreeListLOCALFONT;
  if ( *(_QWORD *)(v4 + 40) != (v4 ^ (unsigned __int64)plfFreeListLOCALFONT) )
  {
    memset_0(&ExceptionRecord, 0, sizeof(ExceptionRecord));
    ExceptionRecord.ExceptionCode = -1073741595;
    ExceptionRecord.ExceptionAddress = "plfCreateLOCALFONT";
    ExceptionRecord.ExceptionFlags = 1;
    RtlRaiseException(&ExceptionRecord);
    v5 = plfFreeListLOCALFONT;
  }
  if ( v5 )
    *((_QWORD *)v5 + 4) = v4;
  *(_DWORD *)v4 = v3;
  *(_QWORD *)(v4 + 16) = 0;
  if ( !(unsigned int)InsertCFontCache((struct tagENUMLOGFONTEXDVW *)a1) )
  {
    vFreeToLOCALFONTLookAside((struct _LOCALFONT *)v4);
    goto LABEL_17;
  }
LABEL_7:
  RtlLeaveCriticalSection(&semLocal);
  if ( v4 )
  {
    dvNumAxes = a1->elfDesignVector.dvNumAxes;
    if ( dvNumAxes > 0x10 || (v1 = NtGdiHfontCreate(a1, 4 * dvNumAxes + 356, 0, 0, v4)) == 0 )
    {
      RtlEnterCriticalSection(&semLocal);
      vDeleteLOCALFONT((struct _LOCALFONT *)v4);
      RtlLeaveCriticalSection(&semLocal);
    }
  }
  return (HFONT)GdiTrackHCreate(v1);
}

```

## disassembly

```asm
0x18002fb70  push    rbx
0x18002fb72  push    rbp
0x18002fb73  push    rsi
0x18002fb74  push    rdi
0x18002fb75  sub     rsp, 0E8h
0x18002fb7c  mov     rax, cs:__security_cookie
0x18002fb83  xor     rax, rsp
0x18002fb86  mov     [rsp+108h+var_38], rax
0x18002fb8e  mov     eax, [rcx+0Ch]
0x18002fb91  xor     esi, esi
0x18002fb93  or      eax, [rcx+8]
0x18002fb96  mov     rdi, rcx
0x18002fb99  mov     ebp, esi
0x18002fb9b  lea     rcx, semLocal; CriticalSection
0x18002fba2  setnz   bpl
0x18002fba6  call    cs:__imp_RtlEnterCriticalSection
0x18002fbad  nop     dword ptr [rax+rax+00h]
0x18002fbb2  mov     rbx, cs:?plfFreeListLOCALFONT@@3PEAU_LOCALFONT@@EA; _LOCALFONT * plfFreeListLOCALFONT
0x18002fbb9  test    rbx, rbx
0x18002fbbc  jz      loc_18002FC83
0x18002fbc2  mov     rcx, [rbx+18h]
0x18002fbc6  mov     rax, rcx
0x18002fbc9  mov     cs:?plfFreeListLOCALFONT@@3PEAU_LOCALFONT@@EA, rcx; _LOCALFONT * plfFreeListLOCALFONT
0x18002fbd0  xor     rax, rbx
0x18002fbd3  mov     cs:?plfFreeListLOCALFONTCopy@@3PEAU_LOCALFONT@@EA, rcx; _LOCALFONT * plfFreeListLOCALFONTCopy
0x18002fbda  cmp     [rbx+28h], rax
0x18002fbde  jnz     loc_18002FD0B
0x18002fbe4  test    rcx, rcx
0x18002fbe7  jz      short loc_18002FBED
0x18002fbe9  mov     [rcx+20h], rbx
0x18002fbed  lea     r8, [rbx+10h]
0x18002fbf1  mov     [rbx], ebp
0x18002fbf3  lea     rdx, [rbx+8]
0x18002fbf7  mov     [r8], rsi
0x18002fbfa  mov     rcx, rdi; struct tagENUMLOGFONTEXDVW *
0x18002fbfd  call    InsertCFontCache
0x18002fc02  test    eax, eax
0x18002fc04  jz      loc_18002FD56
0x18002fc0a  lea     rcx, semLocal; CriticalSection
0x18002fc11  call    cs:__imp_RtlLeaveCriticalSection
0x18002fc18  nop     dword ptr [rax+rax+00h]
0x18002fc1d  test    rbx, rbx
0x18002fc20  jz      short loc_18002FC5E
0x18002fc22  mov     edx, [rdi+160h]
0x18002fc28  cmp     edx, 10h
0x18002fc2b  ja      loc_18002FD65
0x18002fc31  lea     edx, ds:164h[rdx*4]
0x18002fc38  mov     [rsp+108h+var_E8], rbx
0x18002fc3d  xor     r9d, r9d
0x18002fc40  xor     r8d, r8d
0x18002fc43  mov     rcx, rdi
0x18002fc46  call    cs:__imp_NtGdiHfontCreate
0x18002fc4d  nop     dword ptr [rax+rax+00h]
0x18002fc52  mov     rsi, rax
0x18002fc55  test    rax, rax
0x18002fc58  jz      loc_18002FD65
0x18002fc5e  mov     rcx, rsi
0x18002fc61  call    GdiTrackHCreate
0x18002fc66  mov     rcx, [rsp+108h+var_38]
0x18002fc6e  xor     rcx, rsp; StackCookie
0x18002fc71  call    __security_check_cookie
0x18002fc76  add     rsp, 0E8h
0x18002fc7d  pop     rdi
0x18002fc7e  pop     rsi
0x18002fc7f  pop     rbp
0x18002fc80  pop     rbx
0x18002fc81  retn
0x18002fc83  mov     rcx, gs:60h
0x18002fc8c  xor     edx, edx; Flags
0x18002fc8e  mov     r8d, 1E0h; Size
0x18002fc94  mov     rcx, [rcx+30h]; HeapHandle
0x18002fc98  call    cs:__imp_RtlAllocateHeap
0x18002fc9f  nop     dword ptr [rax+rax+00h]
0x18002fca4  mov     rbx, rax
0x18002fca7  test    rax, rax
0x18002fcaa  jz      short loc_18002FCF8
0x18002fcac  mov     r9d, 1
0x18002fcb2  mov     [rax+18h], rsi
0x18002fcb6  mov     [rax+28h], rax
0x18002fcba  mov     [rax+20h], rsi
0x18002fcbe  lea     r8d, [r9+2Fh]
0x18002fcc2  lea     rdx, [r8+rbx]
0x18002fcc6  inc     r9
0x18002fcc9  lea     rcx, [rbx-30h]
0x18002fccd  mov     [rdx+20h], rsi
0x18002fcd1  add     rcx, r8
0x18002fcd4  mov     rax, rdx
0x18002fcd7  xor     rax, rcx
0x18002fcda  mov     [rdx+18h], rcx
0x18002fcde  add     r8, 30h ; '0'
0x18002fce2  mov     [rdx+28h], rax
0x18002fce6  cmp     r9, 0Ah
0x18002fcea  jnz     short loc_18002FCC2
0x18002fcec  add     rbx, 1B0h
0x18002fcf3  jmp     loc_18002FBC2
0x18002fcf8  mov     ecx, 8
0x18002fcfd  call    cs:__imp_GdiSetLastError
0x18002fd04  nop     dword ptr [rax+rax+00h]
0x18002fd09  jmp     short loc_18002FD5E
0x18002fd0b  xor     edx, edx; Val
0x18002fd0d  lea     rcx, [rsp+108h+ExceptionRecord]; void *
0x18002fd12  mov     r8d, 98h; Size
0x18002fd18  call    memset_0
0x18002fd1d  lea     rax, aPlfcreatelocal; "plfCreateLOCALFONT"
0x18002fd24  mov     [rsp+108h+ExceptionRecord.ExceptionCode], 0C00000E5h
0x18002fd2c  lea     rcx, [rsp+108h+ExceptionRecord]; ExceptionRecord
0x18002fd31  mov     [rsp+108h+ExceptionRecord.ExceptionAddress], rax
0x18002fd36  mov     [rsp+108h+ExceptionRecord.ExceptionFlags], 1
0x18002fd3e  call    cs:__imp_RtlRaiseException
0x18002fd45  nop     dword ptr [rax+rax+00h]
0x18002fd4a  mov     rcx, cs:?plfFreeListLOCALFONT@@3PEAU_LOCALFONT@@EA; _LOCALFONT * plfFreeListLOCALFONT
0x18002fd51  jmp     loc_18002FBE4
0x18002fd56  mov     rcx, rbx; struct _LOCALFONT *
0x18002fd59  call    ?vFreeToLOCALFONTLookAside@@YAXPEAU_LOCALFONT@@@Z; vFreeToLOCALFONTLookAside(_LOCALFONT *)
0x18002fd5e  xor     ebx, ebx
0x18002fd60  jmp     loc_18002FC0A
0x18002fd65  lea     rcx, semLocal; CriticalSection
0x18002fd6c  call    cs:__imp_RtlEnterCriticalSection
0x18002fd73  nop     dword ptr [rax+rax+00h]
0x18002fd78  mov     rcx, rbx; struct _LOCALFONT *
0x18002fd7b  call    ?vDeleteLOCALFONT@@YAXPEAU_LOCALFONT@@@Z; vDeleteLOCALFONT(_LOCALFONT *)
0x18002fd80  lea     rcx, semLocal; CriticalSection
0x18002fd87  call    cs:__imp_RtlLeaveCriticalSection
0x18002fd8e  nop     dword ptr [rax+rax+00h]
0x18002fd93  jmp     loc_18002FC5E
```
