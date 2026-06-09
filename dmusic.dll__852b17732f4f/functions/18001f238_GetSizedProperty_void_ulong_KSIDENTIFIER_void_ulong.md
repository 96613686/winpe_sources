# GetSizedProperty(void *,ulong,KSIDENTIFIER *,void * *,ulong *)

- ea: `0x18001f238`
- end: `0x18001f301`
- name: `?GetSizedProperty@@YAHPEAXKPEAUKSIDENTIFIER@@PEAPEAXPEAK@Z`
- size: `201`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, unsigned int@<edx>, struct KSIDENTIFIER *@<r8>, void **@<r9>, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18001e528`
- `0x18001ec08`

## callees

- `0x180016080`
- `0x18001f238`
- `0x1800212e4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f28b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f28b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f2e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f2e3`

## pseudocode

```c
_BOOL8 __fastcall GetSizedProperty(void *a1, unsigned int a2, struct KSIDENTIFIER *a3, void **a4, unsigned int *a5)
{
  BOOL v5; // ebx
  HLOCAL v10; // rax
  unsigned int *v12; // rsi
  SIZE_T uBytes; // [rsp+98h] [rbp+20h] BYREF

  v5 = 0;
  *a4 = 0;
  LODWORD(uBytes) = 0;
  if ( (int)SyncIoctl(a1, 0x2F0003u, a3, a2, 0, 0, (LPDWORD)&uBytes) >= 0 )
  {
    v10 = LocalAlloc(0x40u, (unsigned int)uBytes);
    *a4 = v10;
    if ( !v10 )
    {
      *a5 = 0;
      return 0;
    }
    v12 = a5;
    v5 = Property(a1, a2, a3, uBytes, v10, a5);
    if ( v5 )
    {
      if ( *v12 != (_DWORD)uBytes )
      {
        LocalFree(*a4);
        v5 = 0;
        *a4 = 0;
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18001f238  mov     r11, rsp
0x18001f23b  push    rbx
0x18001f23c  push    rbp
0x18001f23d  push    rsi
0x18001f23e  push    rdi
0x18001f23f  push    r14
0x18001f241  push    r15
0x18001f243  sub     rsp, 48h
0x18001f247  xor     ebx, ebx
0x18001f249  mov     qword ptr [r9], 0
0x18001f250  lea     rax, [r11+20h]
0x18001f254  mov     [r11+20h], ebx
0x18001f258  mov     [r11-48h], rax
0x18001f25c  mov     rdi, r9
0x18001f25f  mov     r14d, edx
0x18001f262  mov     [rsp+78h+var_50], ebx; DWORD
0x18001f266  mov     r9d, edx; unsigned int
0x18001f269  mov     [r11-58h], rbx
0x18001f26d  mov     edx, 2F0003h; unsigned int
0x18001f272  mov     rbp, r8
0x18001f275  mov     r15, rcx
0x18001f278  call    ?SyncIoctl@@YAJPEAXK0K0KPEAK@Z; SyncIoctl(void *,ulong,void *,ulong,void *,ulong,ulong *)
0x18001f27d  test    eax, eax
0x18001f27f  js      short loc_18001F2F2
0x18001f281  mov     edx, dword ptr [rsp+78h+uBytes]; uBytes
0x18001f288  lea     ecx, [rbx+40h]; uFlags
0x18001f28b  call    cs:__imp_LocalAlloc
0x18001f291  mov     [rdi], rax
0x18001f294  test    rax, rax
0x18001f297  jnz     short loc_18001F2A7
0x18001f299  mov     rax, [rsp+78h+arg_20]
0x18001f2a1  mov     [rax], ebx
0x18001f2a3  xor     eax, eax
0x18001f2a5  jmp     short loc_18001F2F4
0x18001f2a7  mov     rsi, [rsp+78h+arg_20]
0x18001f2af  mov     r8, rbp; struct KSIDENTIFIER *
0x18001f2b2  mov     r9d, dword ptr [rsp+78h+uBytes]; unsigned int
0x18001f2ba  mov     edx, r14d; unsigned int
0x18001f2bd  mov     qword ptr [rsp+78h+var_50], rsi; unsigned int *
0x18001f2c2  mov     rcx, r15; void *
0x18001f2c5  mov     [rsp+78h+var_58], rax; void *
0x18001f2ca  call    ?Property@@YAHPEAXKPEAUKSIDENTIFIER@@K0PEAK@Z; Property(void *,ulong,KSIDENTIFIER *,ulong,void *,ulong *)
0x18001f2cf  mov     ebx, eax
0x18001f2d1  test    eax, eax
0x18001f2d3  jz      short loc_18001F2F2
0x18001f2d5  mov     ecx, dword ptr [rsp+78h+uBytes]
0x18001f2dc  cmp     [rsi], ecx
0x18001f2de  jz      short loc_18001F2F2
0x18001f2e0  mov     rcx, [rdi]; hMem
0x18001f2e3  call    cs:__imp_LocalFree
0x18001f2e9  xor     ebx, ebx
0x18001f2eb  mov     qword ptr [rdi], 0
0x18001f2f2  mov     eax, ebx
0x18001f2f4  add     rsp, 48h
0x18001f2f8  pop     r15
0x18001f2fa  pop     r14
0x18001f2fc  pop     rdi
0x18001f2fd  pop     rsi
0x18001f2fe  pop     rbp
0x18001f2ff  pop     rbx
0x18001f300  retn
```
