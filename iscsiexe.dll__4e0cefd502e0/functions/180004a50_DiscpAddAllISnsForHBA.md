# DiscpAddAllISnsForHBA

- ea: `0x180004a50`
- end: `0x180004af2`
- name: `DiscpAddAllISnsForHBA`
- size: `162`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005720`

## callees

- `0x180004a50`
- `0x180004cf8`

## import_xrefs

- `ISCSIUM!DiscpGetRegistryValue` at `0x180004a96`
- `ISCSIUM!DiscpGetRegistryValue` at `0x180004a96`
- `ISCSIUM!DiscpFreeMemory` at `0x180004ada`
- `ISCSIUM!DiscpFreeMemory` at `0x180004ada`

## pseudocode

```c
__int64 __fastcall DiscpAddAllISnsForHBA(__int64 a1)
{
  __int64 v2; // r8
  _WORD *v3; // rbx
  __int64 v4; // rax
  char v6; // [rsp+20h] [rbp-28h]
  int v7; // [rsp+58h] [rbp+10h] BYREF
  _WORD *v8; // [rsp+60h] [rbp+18h] BYREF

  v8 = 0;
  v6 = 0;
  v7 = 0;
  if ( !(unsigned int)DiscpGetRegistryValue(
                        0,
                        L"Software\\Microsoft\\Windows NT\\CurrentVersion\\iSCSI\\Discovery",
                        L"SNSServerList",
                        7,
                        v6,
                        &v8,
                        &v7) )
  {
    v3 = v8;
    if ( *v8 )
    {
      do
      {
        LOBYTE(v2) = 1;
        DiscpAddRemoveiSNSServerForHBA(a1, v3, v2);
        v4 = -1;
        do
          ++v4;
        while ( v3[v4] );
        v3 += v4 + 1;
      }
      while ( *v3 );
      v3 = v8;
    }
    DiscpFreeMemory(v3);
  }
  return 0;
}

```

## disassembly

```asm
0x180004a50  mov     r11, rsp
0x180004a53  mov     [r11+8], rbx
0x180004a57  mov     [r11+20h], rsi
0x180004a5b  push    rdi
0x180004a5c  sub     rsp, 40h
0x180004a60  xor     esi, esi
0x180004a62  lea     rax, [r11+10h]
0x180004a66  mov     [r11-18h], rax
0x180004a6a  lea     r8, aSnsserverlist; "SNSServerList"
0x180004a71  lea     rax, [r11+18h]
0x180004a75  mov     [r11+18h], rsi
0x180004a79  mov     rdi, rcx
0x180004a7c  mov     [r11-20h], rax
0x180004a80  lea     r9d, [rsi+7]
0x180004a84  mov     [rsp+48h+var_28], sil
0x180004a89  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows NT\\Curren"...
0x180004a90  mov     [rsp+48h+arg_8], esi
0x180004a94  xor     ecx, ecx
0x180004a96  call    cs:__imp_DiscpGetRegistryValue
0x180004a9c  test    eax, eax
0x180004a9e  jnz     short loc_180004AE0
0x180004aa0  mov     rbx, [rsp+48h+arg_10]
0x180004aa5  cmp     [rbx], si
0x180004aa8  jz      short loc_180004AD7
0x180004aaa  mov     r8b, 1
0x180004aad  mov     rdx, rbx
0x180004ab0  mov     rcx, rdi
0x180004ab3  call    DiscpAddRemoveiSNSServerForHBA
0x180004ab8  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004abc  inc     rax
0x180004abf  cmp     [rbx+rax*2], si
0x180004ac3  jnz     short loc_180004ABC
0x180004ac5  lea     rbx, [rbx+rax*2]
0x180004ac9  add     rbx, 2
0x180004acd  cmp     [rbx], si
0x180004ad0  jnz     short loc_180004AAA
0x180004ad2  mov     rbx, [rsp+48h+arg_10]
0x180004ad7  mov     rcx, rbx
0x180004ada  call    cs:__imp_DiscpFreeMemory
0x180004ae0  mov     rbx, [rsp+48h+arg_0]
0x180004ae5  xor     eax, eax
0x180004ae7  mov     rsi, [rsp+48h+arg_18]
0x180004aec  add     rsp, 40h
0x180004af0  pop     rdi
0x180004af1  retn
```
