# ProcessChunkAndUpdateBlockState_0

- ea: `0x1400287a0`
- end: `0x140028943`
- name: `ProcessChunkAndUpdateBlockState_0`
- size: `419`
- prototype: `void __fastcall(__int64, _DWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14001dab0`
- `0x140022c10`
- `0x14002dde0`

## callees

- `0x140013c90`
- `0x1400287a0`
- `0x1400372c0`

## import_xrefs

- `rdbss!RxLowIoGetBufferAddress` at `0x1400288e0`
- `rdbss!RxLowIoGetBufferAddress` at `0x1400288e0`

## pseudocode

```c
void __fastcall ProcessChunkAndUpdateBlockState_0(__int64 a1, _DWORD *a2)
{
  int v2; // edi
  unsigned int v5; // r15d
  unsigned int v6; // ebp
  unsigned int i; // r14d
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rax
  char *v12; // rcx
  char *BufferAddress; // rax
  char *v14; // r9

  v2 = a2[12];
  if ( v2 < 0 || (a2[1] & 0x400) != 0 )
  {
    if ( !v2 || v2 == -2147483643 || (v5 = 0, v2 == 1073741877) )
      v5 = a2[187];
    v6 = 0;
    for ( i = v5; v6 < a2[347]; ++v6 )
    {
      *(_DWORD *)(a1 + 8LL * (v6 + a2[346]) + 2496) = v2;
      if ( i )
      {
        v8 = v6 + a2[346];
        if ( i <= 0x10000 )
        {
          *(_DWORD *)(a1 + 8 * v8 + 2500) = i;
          v9 = i;
        }
        else
        {
          *(_DWORD *)(a1 + 8 * v8 + 2500) = 0x10000;
          v9 = 0x10000;
        }
        i -= v9;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_DDD(
          WPP_GLOBAL_Control->AttachedDevice,
          18,
          WPP_a0b49660c994371bf323b193efb7fcea_Traceguids,
          v6 + a2[346],
          *(_DWORD *)(a1 + 8LL * (v6 + a2[346]) + 2500),
          v2);
      }
    }
    if ( v5 )
    {
      v10 = *(_QWORD *)(a1 + 1024);
      if ( v10 )
      {
        v11 = *(_QWORD *)(a1 + 2456);
        if ( v11 )
        {
          v12 = *(char **)(a1 + 2488);
        }
        else
        {
          BufferAddress = (char *)RxLowIoGetBufferAddress(*(PRX_CONTEXT *)(a1 + 48));
          v10 = *(_QWORD *)(a1 + 1024);
          v12 = BufferAddress;
          v11 = *(_QWORD *)(a1 + 2456);
        }
        if ( !v12 )
          __int2c();
        if ( v11 )
          v14 = &v12[*(unsigned int *)(*(_QWORD *)(a1 + 2464) + 8LL)];
        else
          v14 = v12;
        memmove(&v14[a2[348]], (const void *)((unsigned int)a2[348] + (v10 & 0xFFFFFFFFFFFFFFF8uLL)), v5);
      }
    }
  }
}

```

## disassembly

```asm
0x1400287a0  push    rbx
0x1400287a2  push    rsi
0x1400287a3  push    rdi
0x1400287a4  sub     rsp, 30h
0x1400287a8  mov     edi, [rdx+30h]
0x1400287ab  mov     rbx, rdx
0x1400287ae  mov     rsi, rcx
0x1400287b1  test    edi, edi
0x1400287b3  js      short loc_1400287C2
0x1400287b5  test    dword ptr [rdx+4], 400h
0x1400287bc  jz      loc_14002893A
0x1400287c2  mov     [rsp+48h+arg_0], rbp
0x1400287c7  mov     [rsp+48h+arg_10], r14
0x1400287cc  mov     [rsp+48h+arg_18], r15
0x1400287d1  test    edi, edi
0x1400287d3  jz      short loc_1400287E8
0x1400287d5  cmp     edi, 80000005h
0x1400287db  jz      short loc_1400287E8
0x1400287dd  xor     r15d, r15d
0x1400287e0  cmp     edi, 40000035h
0x1400287e6  jnz     short loc_1400287EF
0x1400287e8  mov     r15d, [rdx+2ECh]
0x1400287ef  xor     ebp, ebp
0x1400287f1  mov     r14d, r15d
0x1400287f4  cmp     [rdx+56Ch], ebp
0x1400287fa  jbe     loc_1400288AC
0x140028800  mov     [rsp+48h+arg_8], r12
0x140028805  lea     r12, WPP_GLOBAL_Control
0x14002880c  mov     eax, [rbx+568h]
0x140028812  add     eax, ebp
0x140028814  mov     [rsi+rax*8+9C0h], edi
0x14002881b  test    r14d, r14d
0x14002881e  jz      short loc_140028851
0x140028820  mov     eax, [rbx+568h]
0x140028826  add     eax, ebp
0x140028828  cmp     r14d, 10000h
0x14002882f  jbe     short loc_140028843
0x140028831  mov     dword ptr [rsi+rax*8+9C4h], 10000h
0x14002883c  mov     eax, 10000h
0x140028841  jmp     short loc_14002884E
0x140028843  mov     [rsi+rax*8+9C4h], r14d
0x14002884b  mov     eax, r14d
0x14002884e  sub     r14d, eax
0x140028851  mov     rcx, cs:WPP_GLOBAL_Control
0x140028858  cmp     rcx, r12
0x14002885b  jz      short loc_140028899
0x14002885d  mov     eax, [rcx+2Ch]
0x140028860  test    al, 2
0x140028862  jz      short loc_140028899
0x140028864  cmp     byte ptr [rcx+29h], 4
0x140028868  jb      short loc_140028899
0x14002886a  mov     r9d, [rbx+568h]
0x140028871  lea     r8, WPP_a0b49660c994371bf323b193efb7fcea_Traceguids
0x140028878  mov     rcx, [rcx+18h]
0x14002887c  add     r9d, ebp
0x14002887f  mov     edx, 12h
0x140028884  mov     [rsp+48h+var_20], edi
0x140028888  mov     eax, [rsi+r9*8+9C4h]
0x140028890  mov     [rsp+48h+var_28], eax
0x140028894  call    WPP_SF_DDD
0x140028899  inc     ebp
0x14002889b  cmp     ebp, [rbx+56Ch]
0x1400288a1  jb      loc_14002880C
0x1400288a7  mov     r12, [rsp+48h+arg_8]
0x1400288ac  mov     r14, [rsp+48h+arg_10]
0x1400288b1  mov     rbp, [rsp+48h+arg_0]
0x1400288b6  test    r15d, r15d
0x1400288b9  jz      short loc_140028935
0x1400288bb  mov     rdx, [rsi+400h]
0x1400288c2  test    rdx, rdx
0x1400288c5  jz      short loc_140028935
0x1400288c7  mov     rax, [rsi+998h]
0x1400288ce  test    rax, rax
0x1400288d1  jz      short loc_1400288DC
0x1400288d3  mov     rcx, [rsi+9B8h]
0x1400288da  jmp     short loc_1400288FD
0x1400288dc  mov     rcx, [rsi+30h]; RxContext
0x1400288e0  call    cs:__imp_RxLowIoGetBufferAddress
0x1400288e7  nop     dword ptr [rax+rax+00h]
0x1400288ec  mov     rdx, [rsi+400h]
0x1400288f3  mov     rcx, rax
0x1400288f6  mov     rax, [rsi+998h]
0x1400288fd  test    rcx, rcx
0x140028900  jnz     short loc_140028904
0x140028902  int     2Ch; Windows NT - assertion failure
0x140028904  test    rax, rax
0x140028907  jz      short loc_140028919
0x140028909  mov     rax, [rsi+9A0h]
0x140028910  mov     r9d, [rax+8]
0x140028914  add     r9, rcx
0x140028917  jmp     short loc_14002891C
0x140028919  mov     r9, rcx
0x14002891c  mov     eax, [rbx+570h]
0x140028922  and     rdx, 0FFFFFFFFFFFFFFF8h
0x140028926  mov     r8d, r15d; Size
0x140028929  add     rdx, rax; Src
0x14002892c  lea     rcx, [rax+r9]; void *
0x140028930  call    memmove
0x140028935  mov     r15, [rsp+48h+arg_18]
0x14002893a  add     rsp, 30h
0x14002893e  pop     rdi
0x14002893f  pop     rsi
0x140028940  pop     rbx
0x140028941  retn
```
