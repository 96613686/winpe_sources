# CtlpDeathTimeout

- ea: `0x1400137ac`
- end: `0x1400138b3`
- name: `CtlpDeathTimeout`
- size: `263`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x140004990`
- `0x1400049d0`

## callees

- `0x140003d58`
- `0x140004204`
- `0x140004374`
- `0x1400076d0`
- `0x140007ac0`
- `0x140011c00`
- `0x1400131e4`
- `0x1400137ac`
- `0x14001cd00`

## pseudocode

```c
void __fastcall CtlpDeathTimeout(__int64 a1)
{
  __int64 v2; // r8
  struct _DEVICE_OBJECT *AttachedDevice; // rbx
  CHAR *StringFromSockAddr; // rax
  CHAR v5[80]; // [rsp+20h] [rbp-68h] BYREF

  memset(v5, 0, 0x41u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    StringFromSockAddr = GetStringFromSockAddr(a1 + 368, v5);
    WPP_SF_s(AttachedDevice, 99, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids, StringFromSockAddr);
  }
  CtlSetState(a1, 7u, v2, 0);
  if ( *(_QWORD *)(a1 + 136) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 100, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids, a1);
    }
    WskConnDisconnectEvent(*(_QWORD *)(a1 + 136), 0);
  }
  else
  {
    CtlCleanup(a1, 0);
  }
}

```

## disassembly

```asm
0x1400137ac  mov     [rsp+arg_8], rbx
0x1400137b1  mov     [rsp+arg_10], rsi
0x1400137b6  push    rdi
0x1400137b7  sub     rsp, 80h
0x1400137be  mov     rax, cs:__security_cookie
0x1400137c5  xor     rax, rsp
0x1400137c8  mov     [rsp+88h+var_18], rax
0x1400137cd  xor     edx, edx; Val
0x1400137cf  mov     rdi, rcx
0x1400137d2  lea     rcx, [rsp+88h+var_68]; void *
0x1400137d7  lea     r8d, [rdx+41h]; Size
0x1400137db  call    memset
0x1400137e0  mov     rbx, cs:WPP_GLOBAL_Control
0x1400137e7  lea     rsi, WPP_GLOBAL_Control
0x1400137ee  cmp     rbx, rsi
0x1400137f1  jz      short loc_14001382C
0x1400137f3  mov     eax, [rbx+2Ch]
0x1400137f6  test    al, 8
0x1400137f8  jz      short loc_14001382C
0x1400137fa  cmp     byte ptr [rbx+29h], 1
0x1400137fe  jb      short loc_14001382C
0x140013800  mov     rbx, [rbx+18h]
0x140013804  lea     rcx, [rdi+170h]
0x14001380b  lea     rdx, [rsp+88h+var_68]
0x140013810  call    GetStringFromSockAddr
0x140013815  mov     r9, rax
0x140013818  lea     r8, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids
0x14001381f  mov     edx, 63h ; 'c'
0x140013824  mov     rcx, rbx
0x140013827  call    WPP_SF_s
0x14001382c  xor     r9d, r9d
0x14001382f  mov     rcx, rdi
0x140013832  lea     edx, [r9+7]
0x140013836  call    CtlSetState
0x14001383b  cmp     qword ptr [rdi+88h], 0
0x140013843  jz      short loc_140013886
0x140013845  mov     rcx, cs:WPP_GLOBAL_Control
0x14001384c  cmp     rcx, rsi
0x14001384f  jz      short loc_140013876
0x140013851  mov     eax, [rcx+2Ch]
0x140013854  test    al, 8
0x140013856  jz      short loc_140013876
0x140013858  cmp     byte ptr [rcx+29h], 1
0x14001385c  jb      short loc_140013876
0x14001385e  mov     rcx, [rcx+18h]
0x140013862  lea     r8, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids
0x140013869  mov     edx, 64h ; 'd'
0x14001386e  mov     r9, rdi
0x140013871  call    WPP_SF_q
0x140013876  mov     rcx, [rdi+88h]
0x14001387d  xor     edx, edx
0x14001387f  call    WskConnDisconnectEvent
0x140013884  jmp     short loc_140013890
0x140013886  xor     edx, edx
0x140013888  mov     rcx, rdi
0x14001388b  call    CtlCleanup
0x140013890  mov     rcx, [rsp+88h+var_18]
0x140013895  xor     rcx, rsp; StackCookie
0x140013898  call    __security_check_cookie
0x14001389d  lea     r11, [rsp+88h+var_8]
0x1400138a5  mov     rbx, [r11+18h]
0x1400138a9  mov     rsi, [r11+20h]
0x1400138ad  mov     rsp, r11
0x1400138b0  pop     rdi
0x1400138b1  retn
```
