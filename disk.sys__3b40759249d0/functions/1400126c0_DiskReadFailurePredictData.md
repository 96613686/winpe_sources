# DiskReadFailurePredictData

- ea: `0x1400126c0`
- end: `0x14001280a`
- name: `DiskReadFailurePredictData`
- size: `330`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140012210`

## callees

- `0x1400126c0`
- `0x140012810`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400127b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400127b2`
- `ntoskrnl!ExAllocatePool2` at `0x1400126fd`
- `ntoskrnl!ExAllocatePool2` at `0x1400126fd`

## pseudocode

```c
__int64 __fastcall DiskReadFailurePredictData(__int64 a1, _DWORD *a2)
{
  int v4; // ecx
  char *Buffer; // rbx
  NTSTATUS v6; // edi
  _DWORD *v7; // rdx
  __int128 *v8; // rcx
  __int64 v9; // rax
  __int128 v10; // xmm0
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF

  v4 = *(_DWORD *)(*(_QWORD *)(a1 + 96) + 16LL);
  if ( v4 == 2 )
  {
    LODWORD(v12) = 556;
    Buffer = (char *)ExAllocatePool2(64, 556, 1631871827);
    if ( Buffer )
    {
      v6 = DiskPerformSmartCommand(a1, 1770754, 176, 208, 0, 0, Buffer, (int *)&v12);
      if ( v6 >= 0 )
      {
        *a2 = 512;
        v7 = a2 + 1;
        v8 = (__int128 *)(Buffer + 44);
        v9 = 4;
        do
        {
          v7 += 32;
          v10 = *v8;
          v8 += 8;
          *((_OWORD *)v7 - 8) = v10;
          *((_OWORD *)v7 - 7) = *(v8 - 7);
          *((_OWORD *)v7 - 6) = *(v8 - 6);
          *((_OWORD *)v7 - 5) = *(v8 - 5);
          *((_OWORD *)v7 - 4) = *(v8 - 4);
          *((_OWORD *)v7 - 3) = *(v8 - 3);
          *((_OWORD *)v7 - 2) = *(v8 - 2);
          *((_OWORD *)v7 - 1) = *(v8 - 1);
          --v9;
        }
        while ( v9 );
      }
      ExFreePoolWithTag(Buffer, 0);
      return (unsigned int)v6;
    }
    else
    {
      return 3221225626LL;
    }
  }
  else if ( v4 == 3 )
  {
    *a2 = 4;
    a2[1] = *(_DWORD *)(a1 + 820);
    return 0;
  }
  else
  {
    return 3221225488LL;
  }
}

```

## disassembly

```asm
0x1400126c0  mov     [rsp+arg_10], rsi
0x1400126c5  push    rdi
0x1400126c6  sub     rsp, 40h
0x1400126ca  mov     rax, [rcx+60h]
0x1400126ce  mov     rdi, rcx
0x1400126d1  mov     rsi, rdx
0x1400126d4  mov     ecx, [rax+10h]
0x1400126d7  cmp     ecx, 2
0x1400126da  jnz     loc_1400127D1
0x1400126e0  mov     edx, 22Ch
0x1400126e5  mov     [rsp+48h+arg_8], rbx
0x1400126ea  mov     ecx, 40h ; '@'
0x1400126ef  mov     dword ptr [rsp+48h+arg_0], 22Ch
0x1400126f7  mov     r8d, 61446353h
0x1400126fd  call    cs:__imp_ExAllocatePool2
0x140012704  nop     dword ptr [rax+rax+00h]
0x140012709  mov     rbx, rax
0x14001270c  test    rax, rax
0x14001270f  jz      loc_140012803
0x140012715  lea     rax, [rsp+48h+arg_0]
0x14001271a  mov     r9b, 0D0h; int
0x14001271d  mov     [rsp+48h+var_10], rax; __int64
0x140012722  mov     r8b, 0B0h; int
0x140012725  mov     [rsp+48h+Buffer], rbx; Buffer
0x14001272a  mov     edx, 1B0502h; int
0x14001272f  mov     [rsp+48h+var_20], 0; char
0x140012734  mov     rcx, rdi; int
0x140012737  mov     [rsp+48h+var_28], 0; char
0x14001273c  call    DiskPerformSmartCommand
0x140012741  mov     edi, eax
0x140012743  test    eax, eax
0x140012745  js      short loc_1400127AD
0x140012747  mov     dword ptr [rsi], 200h
0x14001274d  lea     rdx, [rsi+4]
0x140012751  lea     rcx, [rbx+2Ch]
0x140012755  mov     eax, 4
0x14001275a  lea     rdx, [rdx+80h]
0x140012761  movups  xmm0, xmmword ptr [rcx]
0x140012764  lea     rcx, [rcx+80h]
0x14001276b  movups  xmmword ptr [rdx-80h], xmm0
0x14001276f  movups  xmm1, xmmword ptr [rcx-70h]
0x140012773  movups  xmmword ptr [rdx-70h], xmm1
0x140012777  movups  xmm0, xmmword ptr [rcx-60h]
0x14001277b  movups  xmmword ptr [rdx-60h], xmm0
0x14001277f  movups  xmm1, xmmword ptr [rcx-50h]
0x140012783  movups  xmmword ptr [rdx-50h], xmm1
0x140012787  movups  xmm0, xmmword ptr [rcx-40h]
0x14001278b  movups  xmmword ptr [rdx-40h], xmm0
0x14001278f  movups  xmm1, xmmword ptr [rcx-30h]
0x140012793  movups  xmmword ptr [rdx-30h], xmm1
0x140012797  movups  xmm0, xmmword ptr [rcx-20h]
0x14001279b  movups  xmmword ptr [rdx-20h], xmm0
0x14001279f  movups  xmm1, xmmword ptr [rcx-10h]
0x1400127a3  movups  xmmword ptr [rdx-10h], xmm1
0x1400127a7  sub     rax, 1
0x1400127ab  jnz     short loc_14001275A
0x1400127ad  xor     edx, edx; Tag
0x1400127af  mov     rcx, rbx; P
0x1400127b2  call    cs:__imp_ExFreePoolWithTag
0x1400127b9  nop     dword ptr [rax+rax+00h]
0x1400127be  mov     eax, edi
0x1400127c0  mov     rbx, [rsp+48h+arg_8]
0x1400127c5  mov     rsi, [rsp+48h+arg_10]
0x1400127ca  add     rsp, 40h
0x1400127ce  pop     rdi
0x1400127cf  retn
0x1400127d1  test    ecx, ecx
0x1400127d3  jz      short loc_1400127FC
0x1400127d5  sub     ecx, 1
0x1400127d8  jz      short loc_1400127FC
0x1400127da  cmp     ecx, 2
0x1400127dd  jnz     short loc_1400127FC
0x1400127df  mov     rsi, [rsp+48h+arg_10]
0x1400127e4  mov     dword ptr [rdx], 4
0x1400127ea  mov     eax, [rdi+334h]
0x1400127f0  mov     [rdx+4], eax
0x1400127f3  xor     eax, eax
0x1400127f5  add     rsp, 40h
0x1400127f9  pop     rdi
0x1400127fa  retn
0x1400127fc  mov     eax, 0C0000010h
0x140012801  jmp     short loc_1400127C5
0x140012803  mov     eax, 0C000009Ah
0x140012808  jmp     short loc_1400127C0
```
