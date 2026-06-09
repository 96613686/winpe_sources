# PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData::QueryBootPrefetcher(void)

- ea: `0x18003cc3c`
- end: `0x18003cd42`
- name: `?QueryBootPrefetcher@BootPrefetcherData@PerfDiagStartupResourceUtilizationReporting@@QEAAJXZ`
- size: `262`
- prototype: `__int64 __fastcall(PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016dec`
- `0x18002f06c`
- `0x1800375cc`
- `0x1800c49c4`

## callees

- `0x18003cc3c`
- `0x180056c14`
- `0x180056c20`
- `0x1800cf032`

## import_xrefs

- `ext-ms-win-sysmain-pfapi-l1-1-0!PfRpcSendCommand` at `0x18003ccb5`
- `ext-ms-win-sysmain-pfapi-l1-1-0!PfRpcSendCommand` at `0x18003ccb5`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData::QueryBootPrefetcher(
        PerfDiagStartupResourceUtilizationReporting::BootPrefetcherData *this)
{
  unsigned int v2; // eax
  unsigned int i; // r14d
  _DWORD *v4; // rdi
  signed int v5; // eax
  unsigned int v6; // esi
  size_t Size; // [rsp+48h] [rbp+10h] BYREF
  _DWORD *v9; // [rsp+58h] [rbp+20h]

  v2 = 56;
  LODWORD(Size) = 56;
  for ( i = 0; ; ++i )
  {
    v9 = 0;
    if ( i >= 0xA )
      return (unsigned int)-2147024883;
    v4 = operator new[](v2);
    v9 = v4;
    memset_0(v4, 0, (unsigned int)Size);
    *(_QWORD *)(v4 + 3) = 0;
    v4[5] = 0;
    *v4 = 1;
    v4[1] = 0x200000;
    v4[2] = 2;
    v5 = PfRpcSendCommand(v4, &Size);
    v6 = v5 > 0 ? (unsigned __int16)v5 | 0x80070000 : v5;
    if ( !v5 || v5 == 1753 || v5 == 1058 )
      break;
    if ( v5 != 122 )
      goto LABEL_13;
    LODWORD(Size) = 24 * v4[6] + 32;
    operator delete(v4);
    v2 = Size;
  }
  v6 = 0;
  if ( v4[6] )
  {
    *(_QWORD *)this = v4;
    return v6;
  }
LABEL_13:
  if ( v4 )
    operator delete(v4);
  return v6;
}

```

## disassembly

```asm
0x18003cc3c  mov     [rsp+arg_0], rsi
0x18003cc41  push    rdi
0x18003cc42  push    r14
0x18003cc44  push    r15
0x18003cc46  sub     rsp, 20h
0x18003cc4a  mov     r15, rcx
0x18003cc4d  mov     eax, 38h ; '8'
0x18003cc52  mov     dword ptr [rsp+38h+Size], eax
0x18003cc56  xor     r14d, r14d
0x18003cc59  mov     [rsp+38h+arg_18], 0
0x18003cc62  cmp     r14d, 0Ah
0x18003cc66  jnb     loc_18003CD2C
0x18003cc6c  mov     ecx, eax; unsigned __int64
0x18003cc6e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003cc73  mov     rdi, rax
0x18003cc76  mov     [rsp+38h+arg_18], rax
0x18003cc7b  mov     r8d, dword ptr [rsp+38h+Size]; Size
0x18003cc80  xor     edx, edx; Val
0x18003cc82  mov     rcx, rdi; void *
0x18003cc85  call    memset_0
0x18003cc8a  mov     qword ptr [rdi+0Ch], 0
0x18003cc92  mov     dword ptr [rdi+14h], 0
0x18003cc99  mov     dword ptr [rdi], 1
0x18003cc9f  mov     dword ptr [rdi+4], 200000h
0x18003cca6  mov     dword ptr [rdi+8], 2
0x18003ccad  lea     rdx, [rsp+38h+Size]
0x18003ccb2  mov     rcx, rdi
0x18003ccb5  call    cs:__imp_PfRpcSendCommand
0x18003ccbb  test    eax, eax
0x18003ccbd  jg      short loc_18003CCC3
0x18003ccbf  mov     esi, eax
0x18003ccc1  jmp     short loc_18003CCCC
0x18003ccc3  movzx   esi, ax
0x18003ccc6  or      esi, 80070000h
0x18003cccc  test    eax, eax
0x18003ccce  jz      short loc_18003CD08
0x18003ccd0  cmp     eax, 6D9h
0x18003ccd5  jz      short loc_18003CD08
0x18003ccd7  cmp     eax, 422h
0x18003ccdc  jz      short loc_18003CD08
0x18003ccde  cmp     eax, 7Ah ; 'z'
0x18003cce1  jnz     short loc_18003CD1D
0x18003cce3  mov     eax, [rdi+18h]
0x18003cce6  lea     edx, [rax+rax*2]
0x18003cce9  lea     edx, ds:20h[rdx*8]
0x18003ccf0  mov     dword ptr [rsp+38h+Size], edx
0x18003ccf4  mov     rcx, rdi; Block
0x18003ccf7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003ccfc  inc     r14d
0x18003ccff  mov     eax, dword ptr [rsp+38h+Size]
0x18003cd03  jmp     loc_18003CC59
0x18003cd08  xor     esi, esi
0x18003cd0a  cmp     [rdi+18h], esi
0x18003cd0d  jz      short loc_18003CD1D
0x18003cd0f  mov     [r15], rdi
0x18003cd12  jmp     short loc_18003CD31
0x18003cd14  mov     esi, [rsp+38h+arg_10]
0x18003cd18  mov     rdi, [rsp+38h+arg_18]
0x18003cd1d  test    rdi, rdi
0x18003cd20  jz      short loc_18003CD31
0x18003cd22  mov     rcx, rdi; Block
0x18003cd25  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003cd2a  jmp     short loc_18003CD31
0x18003cd2c  mov     esi, 8007000Dh
0x18003cd31  mov     eax, esi
0x18003cd33  mov     rsi, [rsp+38h+arg_0]
0x18003cd38  add     rsp, 20h
0x18003cd3c  pop     r15
0x18003cd3e  pop     r14
0x18003cd40  pop     rdi
0x18003cd41  retn
```
