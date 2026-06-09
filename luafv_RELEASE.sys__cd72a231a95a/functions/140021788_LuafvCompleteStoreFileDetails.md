# LuafvCompleteStoreFileDetails

- ea: `0x140021788`
- end: `0x140021882`
- name: `LuafvCompleteStoreFileDetails`
- size: `250`
- prototype: `__int64 __fastcall(char, _WORD *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001a378`

## callees

- `0x14001dd40`
- `0x140021788`
- `0x140021888`
- `0x14002194c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140021861`
- `ntoskrnl!RtlInitUnicodeString` at `0x140021861`

## pseudocode

```c
__int64 __fastcall LuafvCompleteStoreFileDetails(char a1, _WORD *a2, __int64 a3)
{
  struct _UNICODE_STRING *v3; // rdi
  int v6; // esi
  unsigned int v8; // edx
  __int16 v9; // r8
  __int64 *v10; // rax
  __int64 v11; // rax
  struct _UNICODE_STRING v12; // xmm0
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // [rsp+20h] [rbp-40h] BYREF
  __int128 v16; // [rsp+28h] [rbp-38h]
  struct _UNICODE_STRING v17; // [rsp+38h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-18h] BYREF

  v3 = (struct _UNICODE_STRING *)(a3 + 16);
  v16 = 0;
  v17 = 0;
  DestinationString = 0;
  if ( a1 )
  {
    v8 = 1;
    v15 = a3 + 16;
    if ( *a2 >= 2u )
    {
      v9 = *(_WORD *)(*(_QWORD *)(a3 + 24) + 2 * ((unsigned __int64)*(unsigned __int16 *)(a3 + 16) >> 1) - 2);
      v10 = &LuafvPathSeparator;
      if ( v9 == 92 )
        v10 = (__int64 *)v16;
      *(_QWORD *)&v16 = v10;
      v11 = 16;
      if ( v9 == 92 )
        v11 = 8;
      v8 = (v9 != 92) + 2;
      *(__int64 *)((char *)&v15 + v11) = (__int64)a2;
    }
    v6 = LuafvAllocateAndBuildString((__int64)&v15, v8, &v17);
    if ( v6 >= 0 )
    {
      LuafvFreePool(*(_QWORD *)(a3 + 24));
      v12 = v17;
      *v3 = v17;
      *(struct _UNICODE_STRING *)a3 = v12;
      RtlInitUnicodeString(&DestinationString, 0);
      LuafvSplitRootPathLeft(a3, &DestinationString, v13, v14);
      *(_WORD *)a3 += 2;
    }
  }
  else
  {
    v6 = 0;
    *(struct _UNICODE_STRING *)a3 = *v3;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140021788  mov     [rsp-18h+arg_0], rbx
0x14002178d  mov     [rsp-18h+arg_8], rsi
0x140021792  push    rbp
0x140021793  push    rdi
0x140021794  push    r14
0x140021796  mov     rbp, rsp
0x140021799  sub     rsp, 60h
0x14002179d  lea     rdi, [r8+10h]
0x1400217a1  xorps   xmm0, xmm0
0x1400217a4  xorps   xmm1, xmm1
0x1400217a7  mov     rbx, r8
0x1400217aa  mov     r9, rdx
0x1400217ad  movdqu  [rbp+var_38], xmm0
0x1400217b2  movups  [rbp+var_28], xmm0
0x1400217b6  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x1400217ba  test    cl, cl
0x1400217bc  jnz     short loc_1400217E0
0x1400217be  movups  xmm0, xmmword ptr [rdi]
0x1400217c1  xor     esi, esi
0x1400217c3  movdqu  xmmword ptr [r8], xmm0
0x1400217c8  lea     r11, [rsp+60h+var_s0]
0x1400217cd  mov     eax, esi
0x1400217cf  mov     rbx, [r11+20h]
0x1400217d3  mov     rsi, [r11+28h]
0x1400217d7  mov     rsp, r11
0x1400217da  pop     r14
0x1400217dc  pop     rdi
0x1400217dd  pop     rbp
0x1400217de  retn
0x1400217e0  mov     edx, 1
0x1400217e5  mov     [rbp+var_40], rdi
0x1400217e9  lea     r14d, [rdx+1]
0x1400217ed  cmp     [r9], r14w
0x1400217f1  jb      short loc_140021833
0x1400217f3  mov     rax, [rdi+8]
0x1400217f7  movzx   ecx, word ptr [rdi]
0x1400217fa  shr     rcx, 1
0x1400217fd  movzx   r8d, word ptr [rax+rcx*2-2]
0x140021803  lea     ecx, [rdx+7]
0x140021806  cmp     r8w, 5Ch ; '\'
0x14002180b  lea     rax, LuafvPathSeparator
0x140021812  cmovz   rax, qword ptr [rbp+var_38]
0x140021817  mov     qword ptr [rbp+var_38], rax
0x14002181b  lea     eax, [rdx+0Fh]
0x14002181e  cmovz   eax, ecx
0x140021821  xor     edx, edx
0x140021823  cmp     r8w, 5Ch ; '\'
0x140021828  setnz   dl
0x14002182b  add     edx, r14d
0x14002182e  mov     [rbp+rax+var_40], r9
0x140021833  lea     r8, [rbp+var_28]
0x140021837  lea     rcx, [rbp+var_40]
0x14002183b  call    LuafvAllocateAndBuildString
0x140021840  mov     esi, eax
0x140021842  test    eax, eax
0x140021844  js      short loc_1400217C8
0x140021846  mov     rcx, [rbx+18h]
0x14002184a  call    LuafvFreePool
0x14002184f  movups  xmm0, [rbp+var_28]
0x140021853  xor     edx, edx; SourceString
0x140021855  lea     rcx, [rbp+DestinationString]; DestinationString
0x140021859  movdqu  xmmword ptr [rdi], xmm0
0x14002185d  movdqu  xmmword ptr [rbx], xmm0
0x140021861  call    cs:__imp_RtlInitUnicodeString
0x140021868  nop     dword ptr [rax+rax+00h]
0x14002186d  lea     rdx, [rbp+DestinationString]
0x140021871  mov     rcx, rbx
0x140021874  call    LuafvSplitRootPathLeft
0x140021879  add     [rbx], r14w
0x14002187d  jmp     loc_1400217C8
```
