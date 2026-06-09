# vFreeMDC(MDC *)

- ea: `0x180024010`
- end: `0x180024153`
- name: `?vFreeMDC@@YAXPEAVMDC@@@Z`
- size: `323`
- prototype: `void __fastcall(struct MDC *this)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180028200`
- `0x180029e20`
- `0x180029ee4`
- `0x18004c138`

## callees

- `0x180024010`
- `0x18002415c`
- `0x18004c8fc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800240a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800240cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024105`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024122`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800240a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800240cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024105`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024122`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180024148`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180024148`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002412a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002412a`
- `ntdll!RtlFreeHeap` at `0x1800240fa`
- `ntdll!RtlFreeHeap` at `0x1800240fa`

## pseudocode

```c
void __fastcall vFreeMDC(struct MDC *this)
{
  void *v2; // rcx
  _QWORD *v3; // rdi
  _QWORD *v4; // rsi
  unsigned int i; // edi
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // r8

  if ( !gbDisableMetaFiles )
  {
    v2 = (void *)*((_QWORD *)this + 21);
    if ( v2 )
      LocalFree(v2);
    v3 = (_QWORD *)((char *)this + 744);
    v4 = (_QWORD *)*((_QWORD *)this + 93);
    while ( v4 != v3 )
    {
      v8 = v4;
      v4 = (_QWORD *)*v4;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
    }
    *((_QWORD *)this + 94) = (char *)this + 744;
    *v3 = v3;
    if ( *((_QWORD *)this + 19) )
    {
      for ( i = 1; i < *((_DWORD *)this + 36); ++i )
      {
        if ( *(_QWORD *)(*((_QWORD *)this + 19) + 24LL * i) )
          vFreeMHE(*((void **)this + 95), i);
      }
      LocalFree(*((HLOCAL *)this + 19));
    }
    v6 = (void *)*((_QWORD *)this + 2);
    if ( v6 )
    {
      if ( *((char *)this + 32) >= 0 )
        LocalFree(v6);
      else
        MDC::CompleteEMFData(this, 0);
    }
    v7 = (void *)*((_QWORD *)this + 1);
    if ( v7 != (void *)-1LL && CloseHandle(v7) )
      *((_QWORD *)this + 1) = 0;
    if ( (*((_BYTE *)this + 32) & 3) == 3 )
      DeleteFileW((LPCWSTR)this + 108);
    *(_DWORD *)this = 0;
    LocalFree(this);
  }
}

```

## disassembly

```asm
0x180024010  mov     [rsp+arg_0], rbx
0x180024015  mov     [rsp+arg_8], rsi
0x18002401a  push    rdi
0x18002401b  sub     rsp, 20h
0x18002401f  cmp     cs:gbDisableMetaFiles, 0
0x180024026  mov     rbx, rcx
0x180024029  jnz     loc_1800240D5
0x18002402f  mov     rcx, [rcx+0A8h]; hMem
0x180024036  test    rcx, rcx
0x180024039  jnz     loc_180024105
0x18002403f  lea     rdi, [rbx+2E8h]
0x180024046  mov     rsi, [rdi]
0x180024049  cmp     rsi, rdi
0x18002404c  jnz     loc_1800240E5
0x180024052  mov     [rdi+8], rdi
0x180024056  mov     [rdi], rdi
0x180024059  cmp     qword ptr [rbx+98h], 0
0x180024061  jz      short loc_1800240A9
0x180024063  mov     edi, 1
0x180024068  cmp     [rbx+90h], edi
0x18002406e  jbe     short loc_18002409C
0x180024070  mov     eax, edi
0x180024072  lea     rcx, [rax+rax*2]
0x180024076  mov     rax, [rbx+98h]
0x18002407d  cmp     qword ptr [rax+rcx*8], 0
0x180024082  jz      short loc_180024092
0x180024084  mov     rcx, [rbx+2F8h]; void *
0x18002408b  mov     edx, edi; unsigned int
0x18002408d  call    ?vFreeMHE@@YAXPEAXK@Z; vFreeMHE(void *,ulong)
0x180024092  inc     edi
0x180024094  cmp     edi, [rbx+90h]
0x18002409a  jb      short loc_180024070
0x18002409c  mov     rcx, [rbx+98h]; hMem
0x1800240a3  call    cs:__imp_LocalFree
0x1800240a9  mov     rcx, [rbx+10h]; hMem
0x1800240ad  test    rcx, rcx
0x1800240b0  jnz     short loc_180024110
0x1800240b2  mov     rcx, [rbx+8]; hObject
0x1800240b6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800240ba  jnz     short loc_18002412A
0x1800240bc  mov     eax, [rbx+20h]
0x1800240bf  and     eax, 3
0x1800240c2  cmp     al, 3
0x1800240c4  jz      short loc_180024141
0x1800240c6  mov     rcx, rbx; hMem
0x1800240c9  mov     dword ptr [rbx], 0
0x1800240cf  call    cs:__imp_LocalFree
0x1800240d5  mov     rbx, [rsp+28h+arg_0]
0x1800240da  mov     rsi, [rsp+28h+arg_8]
0x1800240df  add     rsp, 20h
0x1800240e3  pop     rdi
0x1800240e4  retn
0x1800240e5  mov     rcx, gs:60h
0x1800240ee  mov     r8, rsi; P
0x1800240f1  mov     rsi, [rsi]
0x1800240f4  xor     edx, edx; Flags
0x1800240f6  mov     rcx, [rcx+30h]; HeapHandle
0x1800240fa  call    cs:__imp_RtlFreeHeap
0x180024100  jmp     loc_180024049
0x180024105  call    cs:__imp_LocalFree
0x18002410b  jmp     loc_18002403F
0x180024110  test    byte ptr [rbx+20h], 80h
0x180024114  jz      short loc_180024122
0x180024116  xor     edx, edx; int
0x180024118  mov     rcx, rbx; this
0x18002411b  call    ?CompleteEMFData@MDC@@QEAAPEAXH@Z; MDC::CompleteEMFData(int)
0x180024120  jmp     short loc_1800240B2
0x180024122  call    cs:__imp_LocalFree
0x180024128  jmp     short loc_1800240B2
0x18002412a  call    cs:__imp_CloseHandle
0x180024130  test    eax, eax
0x180024132  jz      short loc_1800240BC
0x180024134  mov     qword ptr [rbx+8], 0
0x18002413c  jmp     loc_1800240BC
0x180024141  lea     rcx, [rbx+0D8h]; lpFileName
0x180024148  call    cs:__imp_DeleteFileW
0x18002414e  jmp     loc_1800240C6
```
