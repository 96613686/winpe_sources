# GetArguments(int *)

- ea: `0x140003394`
- end: `0x1400034d1`
- name: `?GetArguments@@YAPEAGPEAH@Z`
- size: `317`
- prototype: `unsigned __int16 *__fastcall(int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400014e4`

## callees

- `0x140003394`
- `0x140004d68`
- `0x14000566c`
- `0x140005986`

## import_xrefs

- `KERNEL32!GetCommandLineW` at `0x1400033a2`
- `KERNEL32!GetCommandLineW` at `0x1400033a2`
- `KERNEL32!LocalAlloc` at `0x14000345b`
- `KERNEL32!LocalAlloc` at `0x14000345b`

## pseudocode

```c
unsigned __int16 *__fastcall GetArguments(int *a1)
{
  const wchar_t *CommandLineW; // rbx
  int v3; // edx
  wchar_t v4; // ax
  const wchar_t *v5; // rdx
  wchar_t v6; // cx
  __int64 v7; // rbx
  wchar_t v8; // ax
  __int64 v9; // rax
  __int64 v10; // rsi
  unsigned int v11; // r14d
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rdi

  CommandLineW = GetCommandLineW();
  v3 = wcsncmp_0(L"{28fb17e0-d393-439d-9a21-9474a070473a} ", CommandLineW, 0x27u);
  if ( !v3 )
    CommandLineW += 39;
  *a1 = v3 == 0;
  v4 = *CommandLineW;
  if ( *CommandLineW == 34 )
  {
    do
    {
      v5 = CommandLineW++;
      v6 = *CommandLineW;
    }
    while ( *CommandLineW && v6 != 34 );
    if ( v6 == 34 )
      v4 = v5[2];
    else
      v4 = *CommandLineW;
    v7 = 2;
    if ( v6 != 34 )
      v7 = 1;
    CommandLineW = &v5[v7];
  }
  else
  {
    while ( v4 > 0x20u )
      v4 = *++CommandLineW;
  }
  if ( v4 )
  {
    v8 = *CommandLineW;
    do
    {
      if ( v8 > 0x20u )
        break;
      v8 = *++CommandLineW;
    }
    while ( *CommandLineW );
  }
  v9 = -1;
  do
    ++v9;
  while ( CommandLineW[v9] );
  v10 = (unsigned int)(v9 + 1);
  v11 = v9 + 1;
  v12 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v10);
  v13 = v12;
  if ( v12 && StringCchCopyW(v12, v11, CommandLineW) >= 0 )
  {
    do
    {
      while ( FindOrRemoveCommandSwitch(v13, v10, L"-eval", 1) )
        ;
    }
    while ( FindOrRemoveCommandSwitch(v13, v10, L"-new", 1) || FindOrRemoveCommandSwitch(v13, v10, L"-nowait", 1) );
  }
  return v13;
}

```

## disassembly

```asm
0x140003394  push    rbx
0x140003396  push    rbp
0x140003397  push    rsi
0x140003398  push    rdi
0x140003399  push    r14
0x14000339b  sub     rsp, 20h
0x14000339f  mov     rdi, rcx
0x1400033a2  call    cs:__imp_GetCommandLineW
0x1400033a8  mov     r8d, 27h ; '''; MaxCount
0x1400033ae  lea     rcx, a28fb17e0D39343; "{28fb17e0-d393-439d-9a21-9474a070473a} "
0x1400033b5  mov     rdx, rax; String2
0x1400033b8  mov     rbx, rax
0x1400033bb  call    wcsncmp_0
0x1400033c0  xor     ebp, ebp
0x1400033c2  mov     edx, eax
0x1400033c4  test    eax, eax
0x1400033c6  jnz     short loc_1400033CC
0x1400033c8  add     rbx, 4Eh ; 'N'
0x1400033cc  mov     eax, ebp
0x1400033ce  test    edx, edx
0x1400033d0  mov     r8w, 22h ; '"'
0x1400033d5  mov     r9d, 2
0x1400033db  setz    al
0x1400033de  mov     [rdi], eax
0x1400033e0  movzx   eax, word ptr [rbx]
0x1400033e3  cmp     ax, r8w
0x1400033e7  jnz     short loc_140003420
0x1400033e9  mov     rdx, rbx
0x1400033ec  add     rbx, r9
0x1400033ef  movzx   ecx, word ptr [rbx]
0x1400033f2  test    cx, cx
0x1400033f5  jz      short loc_1400033FD
0x1400033f7  cmp     cx, r8w
0x1400033fb  jnz     short loc_1400033E9
0x1400033fd  cmp     cx, r8w
0x140003401  jnz     short loc_140003409
0x140003403  movzx   eax, word ptr [rdx+4]
0x140003407  jmp     short loc_14000340C
0x140003409  movzx   eax, cx
0x14000340c  mov     ebx, 4
0x140003411  cmovnz  rbx, r9
0x140003415  add     rbx, rdx
0x140003418  jmp     short loc_140003426
0x14000341a  add     rbx, r9
0x14000341d  movzx   eax, word ptr [rbx]
0x140003420  cmp     ax, 20h ; ' '
0x140003424  ja      short loc_14000341A
0x140003426  test    ax, ax
0x140003429  jz      short loc_14000343F
0x14000342b  movzx   eax, word ptr [rbx]
0x14000342e  cmp     ax, 20h ; ' '
0x140003432  ja      short loc_14000343F
0x140003434  add     rbx, r9
0x140003437  movzx   eax, word ptr [rbx]
0x14000343a  test    ax, ax
0x14000343d  jnz     short loc_14000342E
0x14000343f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003443  inc     rax
0x140003446  cmp     [rbx+rax*2], bp
0x14000344a  jnz     short loc_140003443
0x14000344c  lea     esi, [rax+1]
0x14000344f  mov     ecx, 40h ; '@'; uFlags
0x140003454  lea     rdx, [rsi+rsi]; uBytes
0x140003458  mov     r14d, esi
0x14000345b  call    cs:__imp_LocalAlloc
0x140003461  mov     rdi, rax
0x140003464  test    rax, rax
0x140003467  jz      short loc_1400034C3
0x140003469  mov     r8, rbx; unsigned __int16 *
0x14000346c  mov     edx, r14d; unsigned __int64
0x14000346f  mov     rcx, rax; unsigned __int16 *
0x140003472  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140003477  test    eax, eax
0x140003479  js      short loc_1400034C3
0x14000347b  mov     r9b, 1; bool
0x14000347e  lea     r8, aEval; "-eval"
0x140003485  mov     edx, esi; unsigned int
0x140003487  mov     rcx, rdi; unsigned __int16 *
0x14000348a  call    ?FindOrRemoveCommandSwitch@@YA_NPEAGKPEBG_N@Z; FindOrRemoveCommandSwitch(ushort *,ulong,ushort const *,bool)
0x14000348f  test    al, al
0x140003491  jnz     short loc_14000347B
0x140003493  mov     r9b, 1; bool
0x140003496  lea     r8, aNew; "-new"
0x14000349d  mov     edx, esi; unsigned int
0x14000349f  mov     rcx, rdi; unsigned __int16 *
0x1400034a2  call    ?FindOrRemoveCommandSwitch@@YA_NPEAGKPEBG_N@Z; FindOrRemoveCommandSwitch(ushort *,ulong,ushort const *,bool)
0x1400034a7  test    al, al
0x1400034a9  jnz     short loc_14000347B
0x1400034ab  mov     r9b, 1; bool
0x1400034ae  lea     r8, aNowait; "-nowait"
0x1400034b5  mov     edx, esi; unsigned int
0x1400034b7  mov     rcx, rdi; unsigned __int16 *
0x1400034ba  call    ?FindOrRemoveCommandSwitch@@YA_NPEAGKPEBG_N@Z; FindOrRemoveCommandSwitch(ushort *,ulong,ushort const *,bool)
0x1400034bf  test    al, al
0x1400034c1  jnz     short loc_14000347B
0x1400034c3  mov     rax, rdi
0x1400034c6  add     rsp, 20h
0x1400034ca  pop     r14
0x1400034cc  pop     rdi
0x1400034cd  pop     rsi
0x1400034ce  pop     rbp
0x1400034cf  pop     rbx
0x1400034d0  retn
```
