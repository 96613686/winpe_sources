# MakeServiceCall__lambda_3079517f2af4cbfbefea45414700e547_

- ea: `0x18000313c`
- end: `0x1800031a0`
- name: `MakeServiceCall__lambda_3079517f2af4cbfbefea45414700e547___`
- size: `100`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180001290`

## callees

- `0x180001400`
- `0x180001ae0`
- `0x18000313c`
- `0x1800031a8`

## pseudocode

```c
__int64 __fastcall MakeServiceCall__lambda_3079517f2af4cbfbefea45414700e547_(__int64 a1)
{
  int v2; // ecx
  int i; // ebx
  int v4; // edx
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  int v8; // eax

  v2 = 0;
  for ( i = 0; i < 2; ++i )
  {
    if ( (unsigned int)CheckForRpcRetry(v2) )
    {
      v2 = EnsureDSSvcRunning(v5, v4, v6, v7);
      if ( v2 < 0 )
        break;
    }
    v8 = DSCGetSharingTokenInformation(
           **(const unsigned __int16 ***)a1,
           **(unsigned __int16 ****)(a1 + 8),
           **(unsigned __int16 ****)(a1 + 16),
           **(enum _DS_SHARE_PERMISSION ***)(a1 + 24));
    if ( !(unsigned int)CheckForRpcRetry(v8) )
      break;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000313c  mov     [rsp+arg_0], rbx
0x180003141  push    rdi
0x180003142  sub     rsp, 20h
0x180003146  mov     rdi, rcx
0x180003149  xor     ecx, ecx; int
0x18000314b  xor     ebx, ebx
0x18000314d  call    ?CheckForRpcRetry@@YAHJ@Z; CheckForRpcRetry(long)
0x180003152  test    eax, eax
0x180003154  jz      short loc_180003161
0x180003156  call    ?EnsureDSSvcRunning@@YAJXZ; EnsureDSSvcRunning(void)
0x18000315b  mov     ecx, eax
0x18000315d  test    eax, eax
0x18000315f  js      short loc_180003193
0x180003161  mov     r9, [rdi+18h]
0x180003165  mov     r8, [rdi+10h]
0x180003169  mov     rdx, [rdi+8]
0x18000316d  mov     rcx, [rdi]
0x180003170  mov     r9, [r9]; enum _DS_SHARE_PERMISSION *
0x180003173  mov     r8, [r8]; unsigned __int16 **
0x180003176  mov     rdx, [rdx]; unsigned __int16 **
0x180003179  mov     rcx, [rcx]; unsigned __int16 *
0x18000317c  call    ?DSCGetSharingTokenInformation@@YAJPEBGPEAPEAG1PEAW4_DS_SHARE_PERMISSION@@@Z; DSCGetSharingTokenInformation(ushort const *,ushort * *,ushort * *,_DS_SHARE_PERMISSION *)
0x180003181  mov     ecx, eax; int
0x180003183  call    ?CheckForRpcRetry@@YAHJ@Z; CheckForRpcRetry(long)
0x180003188  test    eax, eax
0x18000318a  jz      short loc_180003193
0x18000318c  inc     ebx
0x18000318e  cmp     ebx, 2
0x180003191  jl      short loc_18000314D
0x180003193  mov     rbx, [rsp+28h+arg_0]
0x180003198  mov     eax, ecx
0x18000319a  add     rsp, 20h
0x18000319e  pop     rdi
0x18000319f  retn
```
