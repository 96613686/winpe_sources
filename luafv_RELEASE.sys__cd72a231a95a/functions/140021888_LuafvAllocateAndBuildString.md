# LuafvAllocateAndBuildString

- ea: `0x140021888`
- end: `0x140021943`
- name: `LuafvAllocateAndBuildString`
- size: `187`
- prototype: `__int64 __fastcall(__int64, unsigned int, struct _UNICODE_STRING *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000572c`
- `0x140017360`
- `0x140021788`

## callees

- `0x14001b650`
- `0x14001dd40`
- `0x140021888`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400218f9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400218f9`

## pseudocode

```c
__int64 __fastcall LuafvAllocateAndBuildString(__int64 a1, unsigned int a2, struct _UNICODE_STRING *a3)
{
  unsigned int v3; // r9d
  __int64 v4; // r10
  struct _UNICODE_STRING *v5; // rbp
  unsigned __int16 *v8; // rcx
  NTSTATUS appended; // ebx
  __int64 v10; // rdi
  struct _UNICODE_STRING Destination; // [rsp+20h] [rbp-38h] BYREF

  v3 = 0;
  v4 = 0;
  v5 = a3;
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
    LOBYTE(a3) = 2;
    Destination.MaximumLength = v3;
    Destination.Buffer = (PWSTR)LuafvAllocatePool(1, (unsigned __int16)v3, a3);
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
        LuafvFreePool(Destination.Buffer);
      }
      else
      {
LABEL_8:
        *v5 = Destination;
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
0x140021888  push    rbx
0x14002188a  push    rbp
0x14002188b  push    rsi
0x14002188c  push    rdi
0x14002188d  push    r14
0x14002188f  sub     rsp, 30h
0x140021893  xor     r9d, r9d
0x140021896  xor     r10d, r10d
0x140021899  xorps   xmm0, xmm0
0x14002189c  mov     rbp, r8
0x14002189f  mov     esi, edx
0x1400218a1  mov     r14, rcx
0x1400218a4  movups  xmmword ptr [rsp+58h+Destination.Length], xmm0
0x1400218a9  test    edx, edx
0x1400218ab  jz      short loc_1400218C8
0x1400218ad  mov     rcx, [r14+r10*8]
0x1400218b1  inc     r10d
0x1400218b4  movzx   eax, word ptr [rcx]
0x1400218b7  add     r9d, eax
0x1400218ba  cmp     r10d, esi
0x1400218bd  jb      short loc_1400218AD
0x1400218bf  cmp     r9d, 0FFFEh
0x1400218c6  ja      short loc_14002193C
0x1400218c8  movzx   edx, r9w
0x1400218cc  mov     r8b, 2
0x1400218cf  mov     ecx, 1
0x1400218d4  mov     [rsp+58h+Destination.MaximumLength], dx
0x1400218d9  call    LuafvAllocatePool
0x1400218de  mov     [rsp+58h+Destination.Buffer], rax
0x1400218e3  test    rax, rax
0x1400218e6  jz      short loc_140021935
0x1400218e8  xor     ebx, ebx
0x1400218ea  xor     edi, edi
0x1400218ec  test    esi, esi
0x1400218ee  jz      short loc_140021911
0x1400218f0  mov     rdx, [r14+rdi*8]; Source
0x1400218f4  lea     rcx, [rsp+58h+Destination]; Destination
0x1400218f9  call    cs:__imp_RtlAppendUnicodeStringToString
0x140021900  nop     dword ptr [rax+rax+00h]
0x140021905  mov     ebx, eax
0x140021907  test    eax, eax
0x140021909  js      short loc_140021929
0x14002190b  inc     edi
0x14002190d  cmp     edi, esi
0x14002190f  jb      short loc_1400218F0
0x140021911  movups  xmm0, xmmword ptr [rsp+58h+Destination.Length]
0x140021916  movdqu  xmmword ptr [rbp+0], xmm0
0x14002191b  mov     eax, ebx
0x14002191d  add     rsp, 30h
0x140021921  pop     r14
0x140021923  pop     rdi
0x140021924  pop     rsi
0x140021925  pop     rbp
0x140021926  pop     rbx
0x140021927  retn
0x140021929  mov     rcx, [rsp+58h+Destination.Buffer]
0x14002192e  call    LuafvFreePool
0x140021933  jmp     short loc_14002191B
0x140021935  mov     ebx, 0C000009Ah
0x14002193a  jmp     short loc_14002191B
0x14002193c  mov     ebx, 0C0000001h
0x140021941  jmp     short loc_14002191B
```
