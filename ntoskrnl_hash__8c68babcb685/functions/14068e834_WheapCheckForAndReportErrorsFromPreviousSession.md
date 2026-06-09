# WheapCheckForAndReportErrorsFromPreviousSession

- ea: `0x14068e834`
- end: `0x14068e9c4`
- name: `WheapCheckForAndReportErrorsFromPreviousSession`
- size: `400`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140c8bfe4`

## callees

- `0x140265518`
- `0x14068e834`
- `0x14068ea58`
- `0x14068eb08`
- `0x1406f6f80`
- `0x140bb1410`
- `0x140bb19f0`

## import_xrefs

- `PSHED!PshedGetBootErrorPacket` at `0x14068e870`
- `PSHED!PshedGetBootErrorPacket` at `0x14068e870`
- `PSHED!PshedClearErrorRecord` at `0x14068e953`
- `PSHED!PshedClearErrorRecord` at `0x14068e953`
- `PSHED!PshedReadErrorRecord` at `0x14068e8a4`
- `PSHED!PshedReadErrorRecord` at `0x14068e8a4`

## pseudocode

```c
__int64 WheapCheckForAndReportErrorsFromPreviousSession()
{
  __int64 v0; // rax
  _QWORD *WheaInfo; // rbx
  unsigned int *v2; // rsi
  unsigned int v3; // r14d
  _DWORD *Pool2; // rax
  _DWORD *v5; // rdi
  __int64 i; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v8; // [rsp+70h] [rbp+30h] BYREF
  int v9; // [rsp+78h] [rbp+38h] BYREF
  void *Src; // [rsp+80h] [rbp+40h] BYREF
  PVOID P; // [rsp+88h] [rbp+48h] BYREF

  P = 0;
  v9 = 0;
  i = 0;
  v8 = 0;
  Src = 0;
  if ( (int)PshedGetBootErrorPacket(&v9, &P) < 0 )
    P = 0;
  v0 = 0;
  for ( i = 0; i != -1; v0 = i )
  {
    if ( (int)PshedReadErrorRecord(0, v0, &i, &v8, &Src) < 0 )
      break;
    if ( Src )
    {
      if ( *(_DWORD *)Src == 1380274243 && *((_DWORD *)Src + 5) <= v8 )
      {
        WheaInfo = KeGetPcr()->Prcb.WheaInfo;
        if ( WheaInfo )
        {
          v2 = (unsigned int *)Src;
          v3 = *((_DWORD *)Src + 5) + 40;
          Pool2 = (_DWORD *)ExAllocatePool2(64, v3, 1634035799);
          v5 = Pool2;
          if ( Pool2 )
          {
            Pool2[4] = v3;
            Pool2[6] = 2;
            memmove(Pool2 + 10, v2, v2[5]);
            WheapWorkQueueAddItem(WheaInfo[2], v5);
            PshedClearErrorRecord(
              (unsigned __int16)((unsigned int)HIDWORD(*(_QWORD *)((char *)Src + 108)) >> 8),
              *((_QWORD *)Src + 12));
          }
        }
        ExFreePoolWithTag(Src, 0x44485350u);
      }
      else
      {
        ExFreePoolWithTag(Src, 0x44485350u);
        Src = 0;
      }
    }
  }
  if ( P )
  {
    WheapReportBootError();
    ExFreePoolWithTag(P, 0x44485350u);
    P = 0;
  }
  return WheapProcessEfiBadMemoryPage();
}

```

## disassembly

```asm
0x14068e834  push    rbp
0x14068e836  push    rbx
0x14068e837  push    rsi
0x14068e838  push    rdi
0x14068e839  push    r14
0x14068e83b  mov     rbp, rsp
0x14068e83e  sub     rsp, 40h
0x14068e842  lea     rdx, [rbp+P]
0x14068e846  mov     [rbp+P], 0
0x14068e84e  lea     rcx, [rbp+arg_8]
0x14068e852  mov     [rbp+arg_8], 0
0x14068e859  mov     [rbp+var_10], 0
0x14068e861  mov     [rbp+arg_0], 0
0x14068e868  mov     [rbp+Src], 0
0x14068e870  call    cs:__imp_PshedGetBootErrorPacket
0x14068e877  nop     dword ptr [rax+rax+00h]
0x14068e87c  test    eax, eax
0x14068e87e  jns     short loc_14068E888
0x14068e880  mov     [rbp+P], 0
0x14068e888  xor     eax, eax
0x14068e88a  mov     [rbp+var_10], rax
0x14068e88e  lea     rcx, [rbp+Src]
0x14068e892  mov     rdx, rax
0x14068e895  mov     [rsp+40h+var_20], rcx
0x14068e89a  lea     r9, [rbp+arg_0]
0x14068e89e  xor     ecx, ecx
0x14068e8a0  lea     r8, [rbp+var_10]
0x14068e8a4  call    cs:__imp_PshedReadErrorRecord
0x14068e8ab  nop     dword ptr [rax+rax+00h]
0x14068e8b0  test    eax, eax
0x14068e8b2  js      loc_14068E98F
0x14068e8b8  mov     rcx, [rbp+Src]; P
0x14068e8bc  test    rcx, rcx
0x14068e8bf  jz      loc_14068E981
0x14068e8c5  cmp     dword ptr [rcx], 52455043h
0x14068e8cb  jnz     loc_14068E96F
0x14068e8d1  mov     eax, [rbp+arg_0]
0x14068e8d4  cmp     [rcx+14h], eax
0x14068e8d7  ja      loc_14068E96F
0x14068e8dd  mov     rax, gs:18h
0x14068e8e6  mov     rbx, [rax+6160h]
0x14068e8ed  test    rbx, rbx
0x14068e8f0  jz      short loc_14068E95F
0x14068e8f2  mov     rsi, [rbp+Src]
0x14068e8f6  mov     ecx, 40h ; '@'
0x14068e8fb  mov     r8d, 61656857h
0x14068e901  mov     r14d, [rsi+14h]
0x14068e905  add     r14d, 28h ; '('
0x14068e909  mov     edx, r14d
0x14068e90c  call    ExAllocatePool2
0x14068e911  mov     rdi, rax
0x14068e914  test    rax, rax
0x14068e917  jz      short loc_14068E95F
0x14068e919  mov     [rax+10h], r14d
0x14068e91d  lea     rcx, [rax+28h]; void *
0x14068e921  mov     dword ptr [rax+18h], 2
0x14068e928  mov     rdx, rsi; Src
0x14068e92b  mov     r8d, [rsi+14h]; Size
0x14068e92f  call    memmove
0x14068e934  mov     rcx, [rbx+10h]
0x14068e938  mov     rdx, rdi
0x14068e93b  call    WheapWorkQueueAddItem
0x14068e940  mov     rdx, [rbp+Src]
0x14068e944  mov     rax, [rdx+6Ch]
0x14068e948  mov     rdx, [rdx+60h]
0x14068e94c  shr     rax, 28h
0x14068e950  movzx   ecx, ax
0x14068e953  call    cs:__imp_PshedClearErrorRecord
0x14068e95a  nop     dword ptr [rax+rax+00h]
0x14068e95f  mov     rcx, [rbp+Src]; P
0x14068e963  mov     edx, 44485350h; Tag
0x14068e968  call    ExFreePoolWithTag
0x14068e96d  jmp     short loc_14068E981
0x14068e96f  mov     edx, 44485350h; Tag
0x14068e974  call    ExFreePoolWithTag
0x14068e979  mov     [rbp+Src], 0
0x14068e981  mov     rax, [rbp+var_10]
0x14068e985  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14068e989  jnz     loc_14068E88E
0x14068e98f  mov     rcx, [rbp+P]
0x14068e993  test    rcx, rcx
0x14068e996  jz      short loc_14068E9B3
0x14068e998  call    WheapReportBootError
0x14068e99d  mov     rcx, [rbp+P]; P
0x14068e9a1  mov     edx, 44485350h; Tag
0x14068e9a6  call    ExFreePoolWithTag
0x14068e9ab  mov     [rbp+P], 0
0x14068e9b3  call    WheapProcessEfiBadMemoryPage
0x14068e9b8  add     rsp, 40h
0x14068e9bc  pop     r14
0x14068e9be  pop     rdi
0x14068e9bf  pop     rsi
0x14068e9c0  pop     rbx
0x14068e9c1  pop     rbp
0x14068e9c2  retn
```
