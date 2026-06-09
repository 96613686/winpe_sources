# EtwpCopyLogfileInfoFromOptions(_TRACELOG_CONTEXT *,ETW_OPEN_TRACE_OPTIONS const *,ushort const *,ushort const *)

- ea: `0x1800049dc`
- end: `0x180004b26`
- name: `?EtwpCopyLogfileInfoFromOptions@@YAKPEAU_TRACELOG_CONTEXT@@PEBUETW_OPEN_TRACE_OPTIONS@@PEBG2@Z`
- size: `330`
- prototype: `unsigned int(struct _TRACELOG_CONTEXT *, const struct ETW_OPEN_TRACE_OPTIONS *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180006740`
- `0x180006970`
- `0x180006c60`

## callees

- `0x18000202c`
- `0x1800049dc`
- `0x180006180`

## pseudocode

```c
__int64 __fastcall EtwpCopyLogfileInfoFromOptions(
        struct _TRACELOG_CONTEXT *a1,
        const struct ETW_OPEN_TRACE_OPTIONS *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 v8; // rax
  unsigned int v9; // ebp
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // kr00_8
  unsigned __int16 *v12; // rax
  __int64 v13; // r11
  __int64 v14; // rcx
  unsigned __int64 v15; // rsi
  unsigned __int64 v16; // rax
  unsigned __int16 *v17; // rax
  __int64 v18; // r11

  *((_DWORD *)a1 + 8) |= 0x10000000u;
  *((_DWORD *)a1 + 27) = 0x10000000;
  *((_QWORD *)a1 + 68) = EtwpMapEventToEventRecord;
  if ( (*(_DWORD *)a2 & 0xFFFFFFFE) != 0 )
    return 50;
  if ( (*(_BYTE *)a2 & 1) != 0 )
  {
    *((_DWORD *)a1 + 8) |= 2u;
    *((_DWORD *)a1 + 27) = 268439552;
  }
  if ( !*((_QWORD *)a2 + 3) && !*((_QWORD *)a2 + 1) )
    return 87;
  *((_QWORD *)a1 + 63) = *((_QWORD *)a2 + 1);
  *((_QWORD *)a1 + 65) = *((_QWORD *)a2 + 2);
  *((_QWORD *)a1 + 66) = *((_QWORD *)a2 + 3);
  *((_QWORD *)a1 + 67) = *((_QWORD *)a2 + 4);
  *((_QWORD *)a1 + 10) = 0;
  *((_QWORD *)a1 + 11) = 0;
  if ( a3 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a3[v8] );
    v9 = v8 + 1;
    v11 = (unsigned int)(v8 + 1);
    v10 = 2 * v11;
    if ( !is_mul_ok(v11, 2u) )
      v10 = -1;
    v12 = (unsigned __int16 *)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v12 )
      return 14;
    StringCchCopyW(v12, v9, a3);
    *((_QWORD *)a1 + 10) = v13;
  }
  if ( a4 )
  {
    v14 = -1;
    do
      ++v14;
    while ( a4[v14] );
    v15 = (unsigned int)(v14 + 1);
    v16 = 2 * v15;
    if ( !is_mul_ok(v15, 2u) )
      v16 = -1;
    v17 = (unsigned __int16 *)operator new[](v16, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v17 )
      return 14;
    StringCchCopyW(v17, v15, a4);
    *((_QWORD *)a1 + 11) = v18;
  }
  return 0;
}

```

## disassembly

```asm
0x1800049dc  push    rbx
0x1800049de  push    rbp
0x1800049df  push    rsi
0x1800049e0  push    rdi
0x1800049e1  push    r14
0x1800049e3  push    r15
0x1800049e5  sub     rsp, 28h
0x1800049e9  mov     rbx, rcx
0x1800049ec  mov     eax, 10000000h
0x1800049f1  or      [rcx+20h], eax
0x1800049f4  mov     rdi, r9
0x1800049f7  mov     [rcx+6Ch], eax
0x1800049fa  mov     rsi, r8
0x1800049fd  lea     rcx, ?EtwpMapEventToEventRecord@@YAKPEAU_TRACELOG_CONTEXT@@PEAXPEAU_ETW_EVENT_INFO@@KPEAU_WMI_BUFFER_HEADER@@@Z; EtwpMapEventToEventRecord(_TRACELOG_CONTEXT *,void *,_ETW_EVENT_INFO *,ulong,_WMI_BUFFER_HEADER *)
0x180004a04  mov     [rbx+220h], rcx
0x180004a0b  test    dword ptr [rdx], 0FFFFFFFEh
0x180004a11  jz      short loc_180004A1D
0x180004a13  mov     eax, 32h ; '2'
0x180004a18  jmp     loc_180004B19
0x180004a1d  test    byte ptr [rdx], 1
0x180004a20  jz      short loc_180004A2D
0x180004a22  or      dword ptr [rbx+20h], 2
0x180004a26  mov     dword ptr [rbx+6Ch], 10001000h
0x180004a2d  xor     r14d, r14d
0x180004a30  cmp     [rdx+18h], r14
0x180004a34  jnz     short loc_180004A45
0x180004a36  cmp     [rdx+8], r14
0x180004a3a  jnz     short loc_180004A45
0x180004a3c  lea     eax, [r14+57h]
0x180004a40  jmp     loc_180004B19
0x180004a45  mov     rax, [rdx+8]
0x180004a49  or      r15, 0FFFFFFFFFFFFFFFFh
0x180004a4d  mov     [rbx+1F8h], rax
0x180004a54  mov     rax, [rdx+10h]
0x180004a58  mov     [rbx+208h], rax
0x180004a5f  mov     rax, [rdx+18h]
0x180004a63  mov     [rbx+210h], rax
0x180004a6a  mov     rax, [rdx+20h]
0x180004a6e  mov     [rbx+218h], rax
0x180004a75  mov     [rbx+50h], r14
0x180004a79  mov     [rbx+58h], r14
0x180004a7d  test    rsi, rsi
0x180004a80  jz      short loc_180004AC6
0x180004a82  mov     rax, r15
0x180004a85  inc     rax
0x180004a88  cmp     [r8+rax*2], r14w
0x180004a8d  jnz     short loc_180004A85
0x180004a8f  lea     ebp, [rax+1]
0x180004a92  mov     eax, 2
0x180004a97  mul     rbp
0x180004a9a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004aa1  cmovb   rax, r15
0x180004aa5  mov     rcx, rax; unsigned __int64
0x180004aa8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180004aad  mov     r11, rax
0x180004ab0  test    rax, rax
0x180004ab3  jz      short loc_180004AFE
0x180004ab5  mov     r8, rsi; unsigned __int16 *
0x180004ab8  mov     edx, ebp; unsigned __int64
0x180004aba  mov     rcx, rax; unsigned __int16 *
0x180004abd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004ac2  mov     [rbx+50h], r11
0x180004ac6  test    rdi, rdi
0x180004ac9  jz      short loc_180004B17
0x180004acb  mov     rcx, r15
0x180004ace  inc     rcx
0x180004ad1  cmp     [rdi+rcx*2], r14w
0x180004ad6  jnz     short loc_180004ACE
0x180004ad8  lea     esi, [rcx+1]
0x180004adb  mov     eax, 2
0x180004ae0  mul     rsi
0x180004ae3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004aea  cmovb   rax, r15
0x180004aee  mov     rcx, rax; unsigned __int64
0x180004af1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180004af6  mov     r11, rax
0x180004af9  test    rax, rax
0x180004afc  jnz     short loc_180004B05
0x180004afe  mov     eax, 0Eh
0x180004b03  jmp     short loc_180004B19
0x180004b05  mov     r8, rdi; unsigned __int16 *
0x180004b08  mov     rdx, rsi; unsigned __int64
0x180004b0b  mov     rcx, r11; unsigned __int16 *
0x180004b0e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004b13  mov     [rbx+58h], r11
0x180004b17  xor     eax, eax
0x180004b19  add     rsp, 28h
0x180004b1d  pop     r15
0x180004b1f  pop     r14
0x180004b21  pop     rdi
0x180004b22  pop     rsi
0x180004b23  pop     rbp
0x180004b24  pop     rbx
0x180004b25  retn
```
