# CreateFontIndirectExW

- ea: `0x180026af0`
- end: `0x180026ce7`
- name: `CreateFontIndirectExW`
- size: `503`
- prototype: `HFONT __stdcall(const ENUMLOGFONTEXDVW *)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180025fb0`
- `0x180026640`
- `0x180075190`
- `0x180085910`

## callees

- `0x180026af0`
- `0x180026cf0`
- `0x180026dd0`
- `0x180036218`
- `0x1800362a0`
- `0x18007ac50`
- `0x18007ba24`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlRaiseException` at `0x180026c9f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlRaiseException` at `0x180026c9f`
- `GDI32!GdiSetLastError` at `0x180026c64`
- `GDI32!GdiSetLastError` at `0x180026c64`
- `ntdll!RtlAllocateHeap` at `0x180026c05`
- `ntdll!RtlAllocateHeap` at `0x180026c05`
- `ntdll!RtlEnterCriticalSection` at `0x180026b26`
- `ntdll!RtlEnterCriticalSection` at `0x180026cc7`
- `ntdll!RtlEnterCriticalSection` at `0x180026b26`
- `ntdll!RtlEnterCriticalSection` at `0x180026cc7`
- `ntdll!RtlLeaveCriticalSection` at `0x180026b8b`
- `ntdll!RtlLeaveCriticalSection` at `0x180026cdc`
- `ntdll!RtlLeaveCriticalSection` at `0x180026b8b`
- `ntdll!RtlLeaveCriticalSection` at `0x180026cdc`
- `win32u!NtGdiHfontCreate` at `0x180026bba`
- `win32u!NtGdiHfontCreate` at `0x180026bba`

## string_xrefs

- `0x180026c7e`: `plfCreateLOCALFONT`

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
  struct _EXCEPTION_RECORD ExceptionRecord; // [rsp+30h] [rbp-D8h] BYREF

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
0x180026af0  push    rbx
0x180026af2  push    rbp
0x180026af3  push    rsi
0x180026af4  push    rdi
0x180026af5  sub     rsp, 0E8h
0x180026afc  mov     rax, cs:__security_cookie
0x180026b03  xor     rax, rsp
0x180026b06  mov     [rsp+108h+var_38], rax
0x180026b0e  mov     eax, [rcx+0Ch]
0x180026b11  xor     esi, esi
0x180026b13  or      eax, [rcx+8]
0x180026b16  mov     rdi, rcx
0x180026b19  mov     ebp, esi
0x180026b1b  lea     rcx, semLocal; CriticalSection
0x180026b22  setnz   bpl
0x180026b26  call    cs:__imp_RtlEnterCriticalSection
0x180026b2c  mov     rbx, cs:?plfFreeListLOCALFONT@@3PEAU_LOCALFONT@@EA; _LOCALFONT * plfFreeListLOCALFONT
0x180026b33  test    rbx, rbx
0x180026b36  jz      loc_180026BF0
0x180026b3c  mov     rcx, [rbx+18h]
0x180026b40  mov     rax, rcx
0x180026b43  mov     cs:?plfFreeListLOCALFONT@@3PEAU_LOCALFONT@@EA, rcx; _LOCALFONT * plfFreeListLOCALFONT
0x180026b4a  xor     rax, rbx
0x180026b4d  mov     cs:?plfFreeListLOCALFONTCopy@@3PEAU_LOCALFONT@@EA, rcx; _LOCALFONT * plfFreeListLOCALFONTCopy
0x180026b54  cmp     [rbx+28h], rax
0x180026b58  jnz     loc_180026C6C
0x180026b5e  test    rcx, rcx
0x180026b61  jz      short loc_180026B67
0x180026b63  mov     [rcx+20h], rbx
0x180026b67  lea     r8, [rbx+10h]
0x180026b6b  mov     [rbx], ebp
0x180026b6d  lea     rdx, [rbx+8]
0x180026b71  mov     [r8], rsi
0x180026b74  mov     rcx, rdi; struct tagENUMLOGFONTEXDVW *
0x180026b77  call    InsertCFontCache
0x180026b7c  test    eax, eax
0x180026b7e  jz      loc_180026CB1
0x180026b84  lea     rcx, semLocal; CriticalSection
0x180026b8b  call    cs:__imp_RtlLeaveCriticalSection
0x180026b91  test    rbx, rbx
0x180026b94  jz      short loc_180026BCC
0x180026b96  mov     edx, [rdi+160h]
0x180026b9c  cmp     edx, 10h
0x180026b9f  ja      loc_180026CC0
0x180026ba5  lea     edx, ds:164h[rdx*4]
0x180026bac  mov     [rsp+108h+var_E8], rbx
0x180026bb1  xor     r9d, r9d
0x180026bb4  xor     r8d, r8d
0x180026bb7  mov     rcx, rdi
0x180026bba  call    cs:__imp_NtGdiHfontCreate
0x180026bc0  mov     rsi, rax
0x180026bc3  test    rax, rax
0x180026bc6  jz      loc_180026CC0
0x180026bcc  mov     rcx, rsi
0x180026bcf  call    GdiTrackHCreate
0x180026bd4  mov     rcx, [rsp+108h+var_38]
0x180026bdc  xor     rcx, rsp; StackCookie
0x180026bdf  call    __security_check_cookie
0x180026be4  add     rsp, 0E8h
0x180026beb  pop     rdi
0x180026bec  pop     rsi
0x180026bed  pop     rbp
0x180026bee  pop     rbx
0x180026bef  retn
0x180026bf0  mov     rcx, gs:60h
0x180026bf9  xor     edx, edx; Flags
0x180026bfb  mov     r8d, 1E0h; Size
0x180026c01  mov     rcx, [rcx+30h]; HeapHandle
0x180026c05  call    cs:__imp_RtlAllocateHeap
0x180026c0b  mov     rbx, rax
0x180026c0e  test    rax, rax
0x180026c11  jz      short loc_180026C5F
0x180026c13  mov     r9d, 1
0x180026c19  mov     [rax+18h], rsi
0x180026c1d  mov     [rax+28h], rax
0x180026c21  mov     [rax+20h], rsi
0x180026c25  lea     r8d, [r9+2Fh]
0x180026c29  lea     rdx, [r8+rbx]
0x180026c2d  inc     r9
0x180026c30  lea     rcx, [rbx-30h]
0x180026c34  mov     [rdx+20h], rsi
0x180026c38  add     rcx, r8
0x180026c3b  mov     rax, rdx
0x180026c3e  xor     rax, rcx
0x180026c41  mov     [rdx+18h], rcx
0x180026c45  add     r8, 30h ; '0'
0x180026c49  mov     [rdx+28h], rax
0x180026c4d  cmp     r9, 0Ah
0x180026c51  jnz     short loc_180026C29
0x180026c53  add     rbx, 1B0h
0x180026c5a  jmp     loc_180026B3C
0x180026c5f  mov     ecx, 8
0x180026c64  call    cs:__imp_GdiSetLastError
0x180026c6a  jmp     short loc_180026CB9
0x180026c6c  xor     edx, edx; Val
0x180026c6e  lea     rcx, [rsp+108h+ExceptionRecord]; void *
0x180026c73  mov     r8d, 98h; Size
0x180026c79  call    memset_0
0x180026c7e  lea     rax, aPlfcreatelocal; "plfCreateLOCALFONT"
0x180026c85  mov     [rsp+108h+ExceptionRecord.ExceptionCode], 0C00000E5h
0x180026c8d  lea     rcx, [rsp+108h+ExceptionRecord]; ExceptionRecord
0x180026c92  mov     [rsp+108h+ExceptionRecord.ExceptionAddress], rax
0x180026c97  mov     [rsp+108h+ExceptionRecord.ExceptionFlags], 1
0x180026c9f  call    cs:__imp_RtlRaiseException
0x180026ca5  mov     rcx, cs:?plfFreeListLOCALFONT@@3PEAU_LOCALFONT@@EA; _LOCALFONT * plfFreeListLOCALFONT
0x180026cac  jmp     loc_180026B5E
0x180026cb1  mov     rcx, rbx; struct _LOCALFONT *
0x180026cb4  call    ?vFreeToLOCALFONTLookAside@@YAXPEAU_LOCALFONT@@@Z; vFreeToLOCALFONTLookAside(_LOCALFONT *)
0x180026cb9  xor     ebx, ebx
0x180026cbb  jmp     loc_180026B84
0x180026cc0  lea     rcx, semLocal; CriticalSection
0x180026cc7  call    cs:__imp_RtlEnterCriticalSection
0x180026ccd  mov     rcx, rbx; struct _LOCALFONT *
0x180026cd0  call    ?vDeleteLOCALFONT@@YAXPEAU_LOCALFONT@@@Z; vDeleteLOCALFONT(_LOCALFONT *)
0x180026cd5  lea     rcx, semLocal; CriticalSection
0x180026cdc  call    cs:__imp_RtlLeaveCriticalSection
0x180026ce2  jmp     loc_180026BCC
```
