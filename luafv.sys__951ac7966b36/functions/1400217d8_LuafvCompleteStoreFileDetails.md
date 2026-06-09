# LuafvCompleteStoreFileDetails

- ea: `0x1400217d8`
- end: `0x1400218d2`
- name: `LuafvCompleteStoreFileDetails`
- size: `250`
- prototype: `__int64 __fastcall(char, struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001a3c8`

## callees

- `0x14001dd90`
- `0x1400217d8`
- `0x1400218d8`
- `0x14002199c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400218b1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400218b1`

## pseudocode

```c
__int64 __fastcall LuafvCompleteStoreFileDetails(char a1, struct _UNICODE_STRING *a2, struct _UNICODE_STRING *a3)
{
  struct _UNICODE_STRING *v3; // rdi
  int v6; // esi
  unsigned int v8; // edx
  WCHAR v9; // r8
  __int64 *v10; // rax
  __int64 v11; // rax
  struct _UNICODE_STRING v12; // xmm0
  __int64 v13; // r8
  __int64 v14; // r9
  struct _UNICODE_STRING *v15; // [rsp+20h] [rbp-40h] BYREF
  __int128 v16; // [rsp+28h] [rbp-38h]
  struct _UNICODE_STRING v17; // [rsp+38h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-18h] BYREF

  v3 = a3 + 1;
  v16 = 0;
  v17 = 0;
  DestinationString = 0;
  if ( a1 )
  {
    v8 = 1;
    v15 = a3 + 1;
    if ( a2->Length >= 2u )
    {
      v9 = a3[1].Buffer[((unsigned __int64)a3[1].Length >> 1) - 1];
      v10 = &LuafvPathSeparator;
      if ( v9 == 92 )
        v10 = (__int64 *)v16;
      *(_QWORD *)&v16 = v10;
      v11 = 16;
      if ( v9 == 92 )
        v11 = 8;
      v8 = (v9 != 92) + 2;
      *(struct _UNICODE_STRING **)((char *)&v15 + v11) = a2;
    }
    v6 = LuafvAllocateAndBuildString((__int64)&v15, v8, &v17);
    if ( v6 >= 0 )
    {
      LuafvFreePool(a3[1].Buffer);
      v12 = v17;
      *v3 = v17;
      *a3 = v12;
      RtlInitUnicodeString(&DestinationString, 0);
      LuafvSplitRootPathLeft(a3, &DestinationString, v13, v14);
      a3->Length += 2;
    }
  }
  else
  {
    v6 = 0;
    *a3 = *v3;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400217d8  mov     [rsp-18h+arg_0], rbx
0x1400217dd  mov     [rsp-18h+arg_8], rsi
0x1400217e2  push    rbp
0x1400217e3  push    rdi
0x1400217e4  push    r14
0x1400217e6  mov     rbp, rsp
0x1400217e9  sub     rsp, 60h
0x1400217ed  lea     rdi, [r8+10h]
0x1400217f1  xorps   xmm0, xmm0
0x1400217f4  xorps   xmm1, xmm1
0x1400217f7  mov     rbx, r8
0x1400217fa  mov     r9, rdx
0x1400217fd  movdqu  [rbp+var_38], xmm0
0x140021802  movups  [rbp+var_28], xmm0
0x140021806  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x14002180a  test    cl, cl
0x14002180c  jnz     short loc_140021830
0x14002180e  movups  xmm0, xmmword ptr [rdi]
0x140021811  xor     esi, esi
0x140021813  movdqu  xmmword ptr [r8], xmm0
0x140021818  lea     r11, [rsp+60h+var_s0]
0x14002181d  mov     eax, esi
0x14002181f  mov     rbx, [r11+20h]
0x140021823  mov     rsi, [r11+28h]
0x140021827  mov     rsp, r11
0x14002182a  pop     r14
0x14002182c  pop     rdi
0x14002182d  pop     rbp
0x14002182e  retn
0x140021830  mov     edx, 1
0x140021835  mov     [rbp+var_40], rdi
0x140021839  lea     r14d, [rdx+1]
0x14002183d  cmp     [r9], r14w
0x140021841  jb      short loc_140021883
0x140021843  mov     rax, [rdi+8]
0x140021847  movzx   ecx, word ptr [rdi]
0x14002184a  shr     rcx, 1
0x14002184d  movzx   r8d, word ptr [rax+rcx*2-2]
0x140021853  lea     ecx, [rdx+7]
0x140021856  cmp     r8w, 5Ch ; '\'
0x14002185b  lea     rax, LuafvPathSeparator
0x140021862  cmovz   rax, qword ptr [rbp+var_38]
0x140021867  mov     qword ptr [rbp+var_38], rax
0x14002186b  lea     eax, [rdx+0Fh]
0x14002186e  cmovz   eax, ecx
0x140021871  xor     edx, edx
0x140021873  cmp     r8w, 5Ch ; '\'
0x140021878  setnz   dl
0x14002187b  add     edx, r14d
0x14002187e  mov     [rbp+rax+var_40], r9
0x140021883  lea     r8, [rbp+var_28]
0x140021887  lea     rcx, [rbp+var_40]
0x14002188b  call    LuafvAllocateAndBuildString
0x140021890  mov     esi, eax
0x140021892  test    eax, eax
0x140021894  js      short loc_140021818
0x140021896  mov     rcx, [rbx+18h]
0x14002189a  call    LuafvFreePool
0x14002189f  movups  xmm0, [rbp+var_28]
0x1400218a3  xor     edx, edx; SourceString
0x1400218a5  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400218a9  movdqu  xmmword ptr [rdi], xmm0
0x1400218ad  movdqu  xmmword ptr [rbx], xmm0
0x1400218b1  call    cs:__imp_RtlInitUnicodeString
0x1400218b8  nop     dword ptr [rax+rax+00h]
0x1400218bd  lea     rdx, [rbp+DestinationString]
0x1400218c1  mov     rcx, rbx
0x1400218c4  call    LuafvSplitRootPathLeft
0x1400218c9  add     [rbx], r14w
0x1400218cd  jmp     loc_140021818
```
