# CldiCanDoNonCdqCompletion

- ea: `0x140010500`
- end: `0x140010583`
- name: `CldiCanDoNonCdqCompletion`
- size: `131`
- prototype: `char __fastcall(_QWORD *)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140036774`
- `0x14003fbf0`
- `0x1400404c0`
- `0x140041598`
- `0x140041cbc`
- `0x140041d84`
- `0x14006d198`
- `0x140082ae0`

## callees

- `0x140010500`
- `0x140076854`

## import_xrefs

- `FLTMGR!FltCbdqRemoveIo` at `0x14001053c`
- `FLTMGR!FltCbdqRemoveIo` at `0x14001053c`

## pseudocode

```c
char __fastcall CldiCanDoNonCdqCompletion(_QWORD *a1)
{
  __int64 *v1; // r8
  __int64 v3; // rdx
  __int64 v4; // rcx
  struct _FLT_CALLBACK_DATA_QUEUE *Cdq; // rax
  PFLT_CALLBACK_DATA_QUEUE_IO_CONTEXT v6; // rdx
  PFLT_CALLBACK_DATA v7; // rax
  __int64 v8; // rcx
  PFLT_CALLBACK_DATA *v9; // rdx

  v1 = (__int64 *)a1[12];
  if ( !v1
    || (v3 = *v1) == 0
    || (v4 = *(_QWORD *)(v3 + 48), v4 == v3 + 48)
    || v4 != *(_QWORD *)(v3 + 56)
    || (Cdq = (struct _FLT_CALLBACK_DATA_QUEUE *)CldiStreamGetCdq(a1[15], v1 + 1), (v7 = FltCbdqRemoveIo(Cdq, v6)) != 0) )
  {
    v7 = (PFLT_CALLBACK_DATA)(a1 + 3);
    v8 = a1[3];
    if ( *(_QWORD **)(v8 + 8) != a1 + 3 || (v9 = (PFLT_CALLBACK_DATA *)a1[4], *v9 != v7) )
      __fastfail(3u);
    *v9 = (PFLT_CALLBACK_DATA)v8;
    *(_QWORD *)(v8 + 8) = v9;
    a1[4] = a1 + 3;
    *(_QWORD *)&v7->Flags = v7;
    LOBYTE(v7) = 1;
  }
  return (char)v7;
}

```

## disassembly

```asm
0x140010500  push    rbx
0x140010502  sub     rsp, 20h
0x140010506  mov     r8, [rcx+60h]
0x14001050a  mov     rbx, rcx
0x14001050d  test    r8, r8
0x140010510  jz      short loc_140010554
0x140010512  mov     rdx, [r8]
0x140010515  test    rdx, rdx
0x140010518  jz      short loc_140010554
0x14001051a  lea     rax, [rdx+30h]
0x14001051e  mov     rcx, [rax]
0x140010521  cmp     rcx, rax
0x140010524  jz      short loc_140010554
0x140010526  cmp     rcx, [rdx+38h]
0x14001052a  jnz     short loc_140010554
0x14001052c  mov     rcx, [rbx+78h]
0x140010530  lea     rdx, [r8+8]
0x140010534  call    CldiStreamGetCdq
0x140010539  mov     rcx, rax; Cbdq
0x14001053c  call    cs:__imp_FltCbdqRemoveIo
0x140010543  nop     dword ptr [rax+rax+00h]
0x140010548  test    rax, rax
0x14001054b  jnz     short loc_140010554
0x14001054d  add     rsp, 20h
0x140010551  pop     rbx
0x140010552  retn
0x140010554  lea     rax, [rbx+18h]
0x140010558  mov     rcx, [rax]
0x14001055b  cmp     [rcx+8], rax
0x14001055f  jnz     short loc_14001057C
0x140010561  mov     rdx, [rax+8]
0x140010565  cmp     [rdx], rax
0x140010568  jnz     short loc_14001057C
0x14001056a  mov     [rdx], rcx
0x14001056d  mov     [rcx+8], rdx
0x140010571  mov     [rax+8], rax
0x140010575  mov     [rax], rax
0x140010578  mov     al, 1
0x14001057a  jmp     short loc_14001054D
0x14001057c  mov     ecx, 3
0x140010581  int     29h; Win8: RtlFailFast(ecx)
```
