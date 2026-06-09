# SyncOpenFileByPathEx

- ea: `0x18007635c`
- end: `0x180076563`
- name: `SyncOpenFileByPathEx`
- size: `519`
- prototype: `__int64 __fastcall(PHANDLE FileHandle)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180076270`

## callees

- `0x180004c40`
- `0x180014a60`
- `0x180020ef0`
- `0x1800360c0`
- `0x180036394`
- `0x18003c488`
- `0x1800469c0`
- `0x1800728c4`
- `0x180075c38`
- `0x18007635c`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180076473`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180076473`
- `ntdll!RtlFreeHeap` at `0x18007650f`
- `ntdll!RtlFreeHeap` at `0x18007650f`

## string_xrefs

- `0x1800763a4`: `SyncOpenFileByPathEx: Handle: 0x%p Path: 0x%p FileName: 0x%p`
- `0x1800763f0`: `SyncOpenFileByPathEx: DesiredAccess: 0x%x ShareAccess: 0x%x Options: 0x%x`
- `0x180076495`: `SyncOpenFileByPathEx: RtlDosPathNameToNtPathName_U failed for [%ws]`
- `0x180076529`: `SyncOpenFileByPathEx: 0x%x`

## pseudocode

```c
__int64 __fastcall SyncOpenFileByPathEx(PHANDLE FileHandle, __int64 a2, const wchar_t *a3)
{
  CObjectMonitor *v5; // rax
  __int64 v6; // rax
  unsigned int v7; // esi
  wchar_t *v8; // rax
  const WCHAR *v9; // rdi
  unsigned int v10; // ebx
  __int64 v11; // r9
  PWSTR Buffer; // rsi
  int v14; // [rsp+28h] [rbp-60h]
  struct _UNICODE_STRING NtPathName; // [rsp+40h] [rbp-48h] BYREF

  NtPathName = 0;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(
        L"SyncOpenFileByPathEx: Handle: 0x%p Path: 0x%p FileName: 0x%p",
        FileHandle,
        &dword_1800966F4,
        a3);
      v14 = (int)a3;
      WPP_SF_qqq(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        15,
        WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids,
        FileHandle,
        &dword_1800966F4);
      v5 = WPP_GLOBAL_Control;
    }
    if ( v5 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(L"SyncOpenFileByPathEx: DesiredAccess: 0x%x ShareAccess: 0x%x Options: 0x%x", 129, 5);
      WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 12), 16, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids, 129, 5, 0);
    }
  }
  v6 = -1;
  do
    ++v6;
  while ( a3[v6] );
  v7 = v6 + 2;
  v8 = (wchar_t *)SyncAlloc((unsigned int)(2 * (v6 + 2)));
  v9 = v8;
  if ( v8 )
  {
    StringCchCopyW(v8, v7, a3);
    if ( RtlDosPathNameToNtPathName_U(v9, &NtPathName, 0, 0) )
    {
      Buffer = NtPathName.Buffer;
      v10 = SyncCreateFileInternal(FileHandle, 0x81u, 0, v11, 1u, v14, &NtPathName);
    }
    else
    {
      Buffer = 0;
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        SyncTraceOutputInternal(L"SyncOpenFileByPathEx: RtlDosPathNameToNtPathName_U failed for [%ws]", v9);
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 17, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids, v9);
      }
      v10 = -1073741766;
    }
    SyncFree(v9);
    if ( Buffer )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  }
  else
  {
    v10 = -1073741670;
  }
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncOpenFileByPathEx: 0x%x", v10);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 18, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids, v10);
  }
  return v10;
}

```

## disassembly

```asm
0x18007635c  push    rbx
0x18007635e  push    rbp
0x18007635f  push    rsi
0x180076360  push    rdi
0x180076361  push    r14
0x180076363  push    r15
0x180076365  sub     rsp, 58h
0x180076369  xorps   xmm0, xmm0
0x18007636c  mov     rbx, r8
0x18007636f  movups  xmmword ptr [rsp+88h+NtPathName.Length], xmm0
0x180076374  mov     rbp, rcx
0x180076377  mov     rax, cs:WPP_GLOBAL_Control
0x18007637e  lea     r15, WPP_GLOBAL_Control
0x180076385  xor     r14d, r14d
0x180076388  cmp     rax, r15
0x18007638b  jz      loc_18007642D
0x180076391  test    byte ptr [rax+6Ch], 4
0x180076395  jz      short loc_1800763E2
0x180076397  mov     rdx, rcx
0x18007639a  lea     rdi, dword_1800966F4
0x1800763a1  mov     r8, rdi
0x1800763a4  lea     rcx, aSyncopenfileby_0; "SyncOpenFileByPathEx: Handle: 0x%p Path"...
0x1800763ab  mov     r9, rbx
0x1800763ae  call    SyncTraceOutputInternal
0x1800763b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800763ba  lea     edx, [r14+0Fh]
0x1800763be  mov     qword ptr [rsp+88h+var_60], rbx
0x1800763c3  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x1800763ca  mov     r9, rbp
0x1800763cd  mov     qword ptr [rsp+88h+var_68], rdi
0x1800763d2  mov     rcx, [rcx+60h]
0x1800763d6  call    WPP_SF_qqq
0x1800763db  mov     rax, cs:WPP_GLOBAL_Control
0x1800763e2  cmp     rax, r15
0x1800763e5  jz      short loc_18007642D
0x1800763e7  test    byte ptr [rax+6Ch], 4
0x1800763eb  jz      short loc_18007642D
0x1800763ed  xor     r9d, r9d
0x1800763f0  lea     rcx, aSyncopenfileby_3; "SyncOpenFileByPathEx: DesiredAccess: 0x"...
0x1800763f7  lea     edi, [r9+5]
0x1800763fb  mov     r8d, edi
0x1800763fe  lea     edx, [rdi+7Ch]
0x180076401  call    SyncTraceOutputInternal
0x180076406  mov     rcx, cs:WPP_GLOBAL_Control
0x18007640d  lea     edx, [rdi+0Bh]
0x180076410  mov     [rsp+88h+var_60], r14d; int
0x180076415  lea     r9d, [rdi+7Ch]
0x180076419  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x180076420  mov     [rsp+88h+var_68], edi
0x180076424  mov     rcx, [rcx+60h]
0x180076428  call    WPP_SF_DDD
0x18007642d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180076431  inc     rax
0x180076434  cmp     [rbx+rax*2], r14w
0x180076439  jnz     short loc_180076431
0x18007643b  lea     esi, [rax+2]
0x18007643e  lea     ecx, [rsi+rsi]
0x180076441  call    SyncAlloc
0x180076446  mov     rdi, rax
0x180076449  test    rax, rax
0x18007644c  jnz     short loc_180076458
0x18007644e  mov     ebx, 0C000009Ah
0x180076453  jmp     loc_180076515
0x180076458  mov     edx, esi; cchDest
0x18007645a  mov     r8, rbx; pszSrc
0x18007645d  mov     rcx, rdi; pszDest
0x180076460  call    StringCchCopyW
0x180076465  xor     r9d, r9d; DirectoryInfo
0x180076468  lea     rdx, [rsp+88h+NtPathName]; NtPathName
0x18007646d  xor     r8d, r8d; NtFileNamePart
0x180076470  mov     rcx, rdi; DosPathName
0x180076473  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180076479  test    al, al
0x18007647b  jnz     short loc_1800764C7
0x18007647d  mov     rsi, r14
0x180076480  mov     rax, cs:WPP_GLOBAL_Control
0x180076487  cmp     rax, r15
0x18007648a  jz      short loc_1800764C0
0x18007648c  test    byte ptr [rax+6Ch], 1
0x180076490  jz      short loc_1800764C0
0x180076492  mov     rdx, rdi
0x180076495  lea     rcx, aSyncopenfileby; "SyncOpenFileByPathEx: RtlDosPathNameToN"...
0x18007649c  call    SyncTraceOutputInternal
0x1800764a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800764a8  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x1800764af  mov     edx, 11h
0x1800764b4  mov     r9, rdi
0x1800764b7  mov     rcx, [rcx+60h]
0x1800764bb  call    WPP_SF_S
0x1800764c0  mov     ebx, 0C000003Ah
0x1800764c5  jmp     short loc_1800764F0
0x1800764c7  mov     rsi, [rsp+88h+NtPathName.Buffer]
0x1800764cc  lea     rax, [rsp+88h+NtPathName]
0x1800764d1  mov     [rsp+88h+var_58], rax; __int64
0x1800764d6  xor     r8d, r8d
0x1800764d9  mov     edx, 81h
0x1800764de  mov     [rsp+88h+var_68], 1; ULONG
0x1800764e6  mov     rcx, rbp; FileHandle
0x1800764e9  call    SyncCreateFileInternal
0x1800764ee  mov     ebx, eax
0x1800764f0  mov     rcx, rdi
0x1800764f3  call    SyncFree
0x1800764f8  test    rsi, rsi
0x1800764fb  jz      short loc_180076515
0x1800764fd  mov     rcx, gs:60h
0x180076506  mov     r8, rsi; P
0x180076509  xor     edx, edx; Flags
0x18007650b  mov     rcx, [rcx+30h]; HeapHandle
0x18007650f  call    cs:__imp_RtlFreeHeap
0x180076515  mov     rax, cs:WPP_GLOBAL_Control
0x18007651c  cmp     rax, r15
0x18007651f  jz      short loc_180076554
0x180076521  test    byte ptr [rax+6Ch], 8
0x180076525  jz      short loc_180076554
0x180076527  mov     edx, ebx
0x180076529  lea     rcx, aSyncopenfileby_4; "SyncOpenFileByPathEx: 0x%x"
0x180076530  call    SyncTraceOutputInternal
0x180076535  mov     rcx, cs:WPP_GLOBAL_Control
0x18007653c  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x180076543  mov     edx, 12h
0x180076548  mov     r9d, ebx
0x18007654b  mov     rcx, [rcx+60h]
0x18007654f  call    WPP_SF_d
0x180076554  mov     eax, ebx
0x180076556  add     rsp, 58h
0x18007655a  pop     r15
0x18007655c  pop     r14
0x18007655e  pop     rdi
0x18007655f  pop     rsi
0x180076560  pop     rbp
0x180076561  pop     rbx
0x180076562  retn
```
