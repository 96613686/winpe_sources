# LuafvAllocateAndBuildString

- ea: `0x1400218d8`
- end: `0x140021993`
- name: `LuafvAllocateAndBuildString`
- size: `187`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140005a2c`
- `0x1400173b0`
- `0x1400217d8`

## callees

- `0x14001b6a0`
- `0x14001dd90`
- `0x1400218d8`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140021949`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140021949`

## pseudocode

```c
__int64 __fastcall LuafvAllocateAndBuildString(__int64 a1, unsigned int a2, struct _UNICODE_STRING *a3)
{
  unsigned int v3; // r9d
  __int64 v4; // r10
  unsigned __int16 *v8; // rcx
  NTSTATUS appended; // ebx
  __int64 v10; // rdi
  struct _UNICODE_STRING Destination; // [rsp+20h] [rbp-38h] BYREF

  v3 = 0;
  v4 = 0;
  Destination = 0;
  if ( !a2 )
    goto LABEL_4;
  do
  {
    v8 = *(unsigned __int16 **)(a1 + 8 * v4);
    v4 = (unsigned int)(v4 + 1);
    v3 += *v8;
  }
  while ( (unsigned int)v4 < a2 );
  if ( v3 > 0xFFFE )
  {
    return (unsigned int)-1073741823;
  }
  else
  {
LABEL_4:
    Destination.MaximumLength = v3;
    Destination.Buffer = (PWSTR)LuafvAllocatePool(1, (unsigned __int16)v3, 2);
    if ( Destination.Buffer )
    {
      appended = 0;
      v10 = 0;
      if ( a2 )
      {
        while ( 1 )
        {
          appended = RtlAppendUnicodeStringToString(&Destination, *(PCUNICODE_STRING *)(a1 + 8 * v10));
          if ( appended < 0 )
            break;
          v10 = (unsigned int)(v10 + 1);
          if ( (unsigned int)v10 >= a2 )
            goto LABEL_8;
        }
        LuafvFreePool((__int64)Destination.Buffer);
      }
      else
      {
LABEL_8:
        *a3 = Destination;
      }
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1400218d8  push    rbx
0x1400218da  push    rbp
0x1400218db  push    rsi
0x1400218dc  push    rdi
0x1400218dd  push    r14
0x1400218df  sub     rsp, 30h
0x1400218e3  xor     r9d, r9d
0x1400218e6  xor     r10d, r10d
0x1400218e9  xorps   xmm0, xmm0
0x1400218ec  mov     rbp, r8
0x1400218ef  mov     esi, edx
0x1400218f1  mov     r14, rcx
0x1400218f4  movups  xmmword ptr [rsp+58h+Destination.Length], xmm0
0x1400218f9  test    edx, edx
0x1400218fb  jz      short loc_140021918
0x1400218fd  mov     rcx, [r14+r10*8]
0x140021901  inc     r10d
0x140021904  movzx   eax, word ptr [rcx]
0x140021907  add     r9d, eax
0x14002190a  cmp     r10d, esi
0x14002190d  jb      short loc_1400218FD
0x14002190f  cmp     r9d, 0FFFEh
0x140021916  ja      short loc_14002198C
0x140021918  movzx   edx, r9w
0x14002191c  mov     r8b, 2
0x14002191f  mov     ecx, 1
0x140021924  mov     [rsp+58h+Destination.MaximumLength], dx
0x140021929  call    LuafvAllocatePool
0x14002192e  mov     [rsp+58h+Destination.Buffer], rax
0x140021933  test    rax, rax
0x140021936  jz      short loc_140021985
0x140021938  xor     ebx, ebx
0x14002193a  xor     edi, edi
0x14002193c  test    esi, esi
0x14002193e  jz      short loc_140021961
0x140021940  mov     rdx, [r14+rdi*8]; Source
0x140021944  lea     rcx, [rsp+58h+Destination]; Destination
0x140021949  call    cs:__imp_RtlAppendUnicodeStringToString
0x140021950  nop     dword ptr [rax+rax+00h]
0x140021955  mov     ebx, eax
0x140021957  test    eax, eax
0x140021959  js      short loc_140021979
0x14002195b  inc     edi
0x14002195d  cmp     edi, esi
0x14002195f  jb      short loc_140021940
0x140021961  movups  xmm0, xmmword ptr [rsp+58h+Destination.Length]
0x140021966  movdqu  xmmword ptr [rbp+0], xmm0
0x14002196b  mov     eax, ebx
0x14002196d  add     rsp, 30h
0x140021971  pop     r14
0x140021973  pop     rdi
0x140021974  pop     rsi
0x140021975  pop     rbp
0x140021976  pop     rbx
0x140021977  retn
0x140021979  mov     rcx, [rsp+58h+Destination.Buffer]
0x14002197e  call    LuafvFreePool
0x140021983  jmp     short loc_14002196B
0x140021985  mov     ebx, 0C000009Ah
0x14002198a  jmp     short loc_14002196B
0x14002198c  mov     ebx, 0C0000001h
0x140021991  jmp     short loc_14002196B
```
