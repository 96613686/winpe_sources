# DfscCmInterLinkState

- ea: `0x1400284a0`
- end: `0x140028564`
- name: `DfscCmInterLinkState`
- size: `196`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400015c0`
- `0x14001d9b0`

## callees

- `0x140002340`
- `0x14001f040`
- `0x140020d10`
- `0x1400284a0`

## pseudocode

```c
__int64 __fastcall DfscCmInterLinkState(__int64 a1)
{
  unsigned int v2; // esi
  int v3; // eax
  void *v4; // rcx
  int v5; // edi

  v2 = 9;
  v3 = DfscRewritePath(a1, (__int16 *)(*(_QWORD *)(a1 + 280) + 96LL), (const UNICODE_STRING *)(a1 + 208), 0);
  v4 = *(void **)(a1 + 272);
  v5 = v3;
  if ( v4 )
  {
    DfscReferralRelease(v4);
    *(_QWORD *)(a1 + 272) = 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_05cba1b763293f8d98259e004f8588c9_Traceguids, a1, v5);
  if ( v5 >= 0 )
  {
    ++*(_WORD *)(a1 + 290);
    v2 = 0;
    if ( *(_WORD *)(a1 + 290) > (unsigned __int16)word_14000C76C )
      word_14000C76C = *(_WORD *)(a1 + 290);
  }
  *(_DWORD *)(a1 + 316) = v5;
  return v2;
}

```

## disassembly

```asm
0x1400284a0  mov     [rsp+arg_0], rbx
0x1400284a5  mov     [rsp+arg_8], rsi
0x1400284aa  push    rdi
0x1400284ab  sub     rsp, 30h
0x1400284af  mov     rdx, [rcx+118h]
0x1400284b6  lea     r8, [rcx+0D0h]
0x1400284bd  add     rdx, 60h ; '`'
0x1400284c1  xor     r9d, r9d
0x1400284c4  mov     rbx, rcx
0x1400284c7  mov     esi, 9
0x1400284cc  call    DfscRewritePath
0x1400284d1  mov     rcx, [rbx+110h]; P
0x1400284d8  mov     edi, eax
0x1400284da  test    rcx, rcx
0x1400284dd  jz      short loc_1400284EF
0x1400284df  call    DfscReferralRelease
0x1400284e4  mov     qword ptr [rbx+110h], 0
0x1400284ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400284f6  lea     rax, WPP_GLOBAL_Control
0x1400284fd  cmp     rcx, rax
0x140028500  jz      short loc_140028527
0x140028502  test    dword ptr [rcx+2Ch], 400000h
0x140028509  jz      short loc_140028527
0x14002850b  mov     rcx, [rcx+18h]
0x14002850f  lea     r8, WPP_05cba1b763293f8d98259e004f8588c9_Traceguids
0x140028516  mov     edx, 26h ; '&'
0x14002851b  mov     [rsp+38h+var_18], edi
0x14002851f  mov     r9, rbx
0x140028522  call    WPP_SF_qD
0x140028527  test    edi, edi
0x140028529  js      short loc_14002854B
0x14002852b  inc     word ptr [rbx+122h]
0x140028532  xor     esi, esi
0x140028534  movzx   ecx, word ptr [rbx+122h]
0x14002853b  cmp     cx, cs:word_14000C76C
0x140028542  jbe     short loc_14002854B
0x140028544  mov     cs:word_14000C76C, cx
0x14002854b  mov     [rbx+13Ch], edi
0x140028551  mov     eax, esi
0x140028553  mov     rbx, [rsp+38h+arg_0]
0x140028558  mov     rsi, [rsp+38h+arg_8]
0x14002855d  add     rsp, 30h
0x140028561  pop     rdi
0x140028562  retn
```
