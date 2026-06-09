# PsmpSqmPolicyCounters

- ea: `0x1800256b8`
- end: `0x18002588d`
- name: `PsmpSqmPolicyCounters`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180015050`

## callees

- `0x18001622c`
- `0x18001b7e0`
- `0x18001c10c`
- `0x180022640`
- `0x1800256b8`

## import_xrefs

- `ntdll!WinSqmAddToStreamEx` at `0x18002583f`
- `ntdll!WinSqmAddToStreamEx` at `0x18002583f`
- `ntdll!RtlCompareMemoryUlong` at `0x180025738`
- `ntdll!RtlCompareMemoryUlong` at `0x180025738`

## pseudocode

```c
void *PsmpSqmPolicyCounters()
{
  __int64 v0; // rbx
  __int64 v1; // rdi
  __int64 *v2; // rsi
  _DWORD v4[48]; // [rsp+30h] [rbp-D0h] BYREF

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ea75ddd8e0fb35f397d4c69b4e756c64_Traceguids);
  v0 = 0;
  do
  {
    v1 = 0;
    do
    {
      v2 = &PsmpCounters[10 * v1 + 5 * v0];
      if ( RtlCompareMemoryUlong(v2, 0x28u, 0) != 40 )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            11,
            WPP_ea75ddd8e0fb35f397d4c69b4e756c64_Traceguids,
            (unsigned int)v1,
            v0);
        v4[10] = *(_DWORD *)v2;
        v4[14] = *((_DWORD *)v2 + 1);
        v4[18] = *((_DWORD *)v2 + 2);
        v4[22] = *((_DWORD *)v2 + 3);
        v4[26] = *((_DWORD *)v2 + 4);
        v4[30] = *((_DWORD *)v2 + 5);
        v4[34] = *((_DWORD *)v2 + 6);
        v4[38] = *((_DWORD *)v2 + 7);
        v4[42] = *((_DWORD *)v2 + 8);
        v4[46] = *((_DWORD *)v2 + 9);
        v4[0] = 16;
        v4[2] = v1;
        v4[1] = 1;
        v4[4] = 16;
        v4[6] = v0;
        v4[5] = 1;
        v4[8] = 16;
        v4[9] = 1;
        v4[12] = 16;
        v4[13] = 1;
        v4[16] = 16;
        v4[17] = 1;
        v4[20] = 16;
        v4[21] = 1;
        v4[24] = 16;
        v4[25] = 1;
        v4[28] = 16;
        v4[29] = 1;
        v4[32] = 16;
        v4[33] = 1;
        v4[36] = 16;
        v4[37] = 1;
        v4[40] = 16;
        v4[41] = 1;
        v4[44] = 16;
        v4[45] = 1;
        WinSqmAddToStreamEx(0, 10860, 12, v4, 0);
      }
      v1 = (unsigned int)(v1 + 1);
    }
    while ( (int)v1 < 3 );
    v0 = (unsigned int)(v0 + 1);
  }
  while ( (int)v0 < 2 );
  return memset_0(PsmpCounters, 0, 0xF0u);
}

```

## disassembly

```asm
0x1800256b8  push    rbp
0x1800256ba  push    rbx
0x1800256bb  push    rsi
0x1800256bc  push    rdi
0x1800256bd  push    r12
0x1800256bf  push    r13
0x1800256c1  push    r14
0x1800256c3  push    r15
0x1800256c5  lea     rbp, [rsp-8]
0x1800256ca  sub     rsp, 108h
0x1800256d1  mov     rax, cs:__security_cookie
0x1800256d8  xor     rax, rsp
0x1800256db  mov     [rbp+40h+var_50], rax
0x1800256df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800256e6  mov     r15d, 1
0x1800256ec  test    [rcx+1Ch], r15b
0x1800256f0  jz      short loc_18002570C
0x1800256f2  cmp     byte ptr [rcx+19h], 4
0x1800256f6  jb      short loc_18002570C
0x1800256f8  mov     rcx, [rcx+10h]
0x1800256fc  lea     edx, [r15+9]
0x180025700  lea     r8, WPP_ea75ddd8e0fb35f397d4c69b4e756c64_Traceguids
0x180025707  call    WPP_SF_
0x18002570c  xor     ebx, ebx
0x18002570e  lea     r13, PsmpCounters
0x180025715  lea     r12d, [rbx+10h]
0x180025719  xor     edi, edi
0x18002571b  lea     rcx, [rbx+rdi*2]
0x18002571f  xor     r8d, r8d; Pattern
0x180025722  lea     rax, [rcx+rcx*4]
0x180025726  lea     rsi, ds:0[rax*8]
0x18002572e  add     rsi, r13
0x180025731  mov     rcx, rsi; Source
0x180025734  lea     edx, [r8+28h]; Length
0x180025738  call    cs:__imp_RtlCompareMemoryUlong
0x18002573e  cmp     rax, 28h ; '('
0x180025742  jz      loc_180025845
0x180025748  mov     rcx, cs:WPP_GLOBAL_Control
0x18002574f  test    [rcx+1Ch], r15b
0x180025753  jz      short loc_180025777
0x180025755  cmp     byte ptr [rcx+19h], 5
0x180025759  jb      short loc_180025777
0x18002575b  mov     rcx, [rcx+10h]
0x18002575f  lea     r8, WPP_ea75ddd8e0fb35f397d4c69b4e756c64_Traceguids
0x180025766  mov     edx, 0Bh
0x18002576b  mov     [rsp+140h+var_120], ebx
0x18002576f  mov     r9d, edi
0x180025772  call    WPP_SF_Dd
0x180025777  mov     eax, [rsi]
0x180025779  lea     r9, [rsp+140h+var_110]
0x18002577e  mov     [rsp+140h+var_E8], eax
0x180025782  xor     ecx, ecx
0x180025784  mov     eax, [rsi+4]
0x180025787  mov     edx, 2A6Ch
0x18002578c  mov     [rsp+140h+var_D8], eax
0x180025790  mov     eax, [rsi+8]
0x180025793  mov     [rsp+140h+var_C8], eax
0x180025797  lea     r8d, [rcx+0Ch]
0x18002579b  mov     eax, [rsi+0Ch]
0x18002579e  mov     [rbp+40h+var_B8], eax
0x1800257a1  mov     eax, [rsi+10h]
0x1800257a4  mov     [rbp+40h+var_A8], eax
0x1800257a7  mov     eax, [rsi+14h]
0x1800257aa  mov     [rbp+40h+var_98], eax
0x1800257ad  mov     eax, [rsi+18h]
0x1800257b0  mov     [rbp+40h+var_88], eax
0x1800257b3  mov     eax, [rsi+1Ch]
0x1800257b6  mov     [rbp+40h+var_78], eax
0x1800257b9  mov     eax, [rsi+20h]
0x1800257bc  mov     [rbp+40h+var_68], eax
0x1800257bf  mov     eax, [rsi+24h]
0x1800257c2  mov     [rbp+40h+var_58], eax
0x1800257c5  mov     [rsp+140h+var_110], r12d
0x1800257ca  mov     [rsp+140h+var_108], edi
0x1800257ce  mov     [rsp+140h+var_10C], r15d
0x1800257d3  mov     [rsp+140h+var_100], r12d
0x1800257d8  mov     [rsp+140h+var_F8], ebx
0x1800257dc  mov     [rsp+140h+var_FC], r15d
0x1800257e1  mov     [rsp+140h+var_F0], r12d
0x1800257e6  mov     [rsp+140h+var_EC], r15d
0x1800257eb  mov     [rsp+140h+var_E0], r12d
0x1800257f0  mov     [rsp+140h+var_DC], r15d
0x1800257f5  mov     [rsp+140h+var_D0], r12d
0x1800257fa  mov     [rsp+140h+var_CC], r15d
0x1800257ff  mov     [rbp+40h+var_C0], r12d
0x180025803  mov     [rbp+40h+var_BC], r15d
0x180025807  mov     [rbp+40h+var_B0], r12d
0x18002580b  mov     [rbp+40h+var_AC], r15d
0x18002580f  mov     [rbp+40h+var_A0], r12d
0x180025813  mov     [rbp+40h+var_9C], r15d
0x180025817  mov     [rbp+40h+var_90], r12d
0x18002581b  mov     [rbp+40h+var_8C], r15d
0x18002581f  mov     [rbp+40h+var_80], r12d
0x180025823  mov     [rbp+40h+var_7C], r15d
0x180025827  mov     [rbp+40h+var_70], r12d
0x18002582b  mov     [rbp+40h+var_6C], r15d
0x18002582f  mov     [rbp+40h+var_60], r12d
0x180025833  mov     [rbp+40h+var_5C], r15d
0x180025837  mov     [rsp+140h+var_120], 0
0x18002583f  call    cs:__imp_WinSqmAddToStreamEx
0x180025845  add     edi, r15d
0x180025848  cmp     edi, 3
0x18002584b  jl      loc_18002571B
0x180025851  add     ebx, r15d
0x180025854  cmp     ebx, 2
0x180025857  jl      loc_180025719
0x18002585d  xor     edx, edx; Val
0x18002585f  mov     r8d, 0F0h; Size
0x180025865  mov     rcx, r13; void *
0x180025868  call    memset_0
0x18002586d  mov     rcx, [rbp+40h+var_50]
0x180025871  xor     rcx, rsp; StackCookie
0x180025874  call    __security_check_cookie
0x180025879  add     rsp, 108h
0x180025880  pop     r15
0x180025882  pop     r14
0x180025884  pop     r13
0x180025886  pop     r12
0x180025888  pop     rdi
0x180025889  pop     rsi
0x18002588a  pop     rbx
0x18002588b  pop     rbp
0x18002588c  retn
```
