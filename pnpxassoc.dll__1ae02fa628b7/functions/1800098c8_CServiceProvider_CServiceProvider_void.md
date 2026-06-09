# CServiceProvider::CServiceProvider(void)

- ea: `0x1800098c8`
- end: `0x18000996a`
- name: `??0CServiceProvider@@QEAA@XZ`
- size: `162`
- prototype: `CServiceProvider *__fastcall(CServiceProvider *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180006990`
- `0x180006b90`

## callees

- `0x1800098c8`
- `0x18000bce4`

## pseudocode

```c
CServiceProvider *__fastcall CServiceProvider::CServiceProvider(CServiceProvider *this)
{
  *((_DWORD *)this + 8) = 0;
  *(_OWORD *)((char *)this + 40) = 0;
  *(_OWORD *)((char *)this + 56) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_BYTE *)this + 80) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 26) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
  *((_WORD *)this + 54) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_8299e7f36ddb39903502156c86dec960_Traceguids);
  return this;
}

```

## disassembly

```asm
0x1800098c8  mov     [rsp+arg_0], rbx
0x1800098cd  push    rsi
0x1800098ce  sub     rsp, 30h
0x1800098d2  mov     dword ptr [rcx+20h], 0
0x1800098d9  xor     eax, eax
0x1800098db  xorps   xmm0, xmm0
0x1800098de  mov     rbx, rcx
0x1800098e1  movups  xmmword ptr [rcx+28h], xmm0
0x1800098e5  movups  xmmword ptr [rcx+38h], xmm0
0x1800098e9  mov     [rcx+48h], rax
0x1800098ed  mov     [rcx+50h], al
0x1800098f0  mov     [rcx+58h], rax
0x1800098f4  mov     [rcx+60h], rax
0x1800098f8  mov     [rcx+68h], eax
0x1800098fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180009902  lea     rsi, WPP_GLOBAL_Control
0x180009909  cmp     rcx, rsi
0x18000990c  jz      short loc_18000992C
0x18000990e  cmp     byte ptr [rcx+19h], 4
0x180009912  jb      short loc_18000992C
0x180009914  mov     rcx, [rcx+10h]
0x180009918  lea     edx, [rax+0Ah]
0x18000991b  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x180009922  mov     [rsp+38h+var_18], rbx
0x180009927  call    WPP_SF_sq
0x18000992c  xor     eax, eax
0x18000992e  mov     [rbx+6Ch], ax
0x180009932  mov     rcx, cs:WPP_GLOBAL_Control
0x180009939  cmp     rcx, rsi
0x18000993c  jz      short loc_18000995C
0x18000993e  cmp     byte ptr [rcx+19h], 4
0x180009942  jb      short loc_18000995C
0x180009944  mov     rcx, [rcx+10h]
0x180009948  lea     edx, [rax+0Bh]
0x18000994b  lea     r8, WPP_8299e7f36ddb39903502156c86dec960_Traceguids
0x180009952  mov     [rsp+38h+var_18], rbx
0x180009957  call    WPP_SF_sq
0x18000995c  mov     rax, rbx
0x18000995f  mov     rbx, [rsp+38h+arg_0]
0x180009964  add     rsp, 30h
0x180009968  pop     rsi
0x180009969  retn
```
