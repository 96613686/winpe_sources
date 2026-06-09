# CDSLink::HandleLatency(ulong,int,void *,ulong *)

- ea: `0x18000fb80`
- end: `0x18000fc50`
- name: `?HandleLatency@CDSLink@@AEAAJKHPEAXPEAK@Z`
- size: `208`
- prototype: `__int64 __fastcall(CDSLink *__hidden this, unsigned int, int, void *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000fb80`
- `0x18000fc80`

## pseudocode

```c
__int64 __fastcall CDSLink::HandleLatency(CDSLink *this, __int64 a2, int a3, void *a4, unsigned int *a5)
{
  __int64 v7; // r10
  unsigned int *v8; // r11
  unsigned int v9; // edx
  unsigned int v10; // r8d

  if ( *a5 != 4 )
    return 2147942487LL;
  if ( !*((_QWORD *)this + 3) || !CDSLink::IsValidFormat(this, (const struct tWAVEFORMATEX *)((char *)this + 84)) )
    return 2289570097LL;
  if ( a3 )
  {
    v9 = *v8;
    if ( *v8 >= 5 )
    {
      if ( v9 > 0x3E8 )
        v9 = 1000;
    }
    else
    {
      v9 = 5;
    }
    *(_DWORD *)(v7 + 216) = ((*(_DWORD *)(v7 + 92) * v9 + 500) / 0x3E8) >> *(_WORD *)(v7 + 86) << *(_WORD *)(v7 + 86);
    return 0;
  }
  else
  {
    v10 = *(_DWORD *)(v7 + 92);
    if ( v10 )
      *v8 = ((v10 >> 1) + 1000 * *(_DWORD *)(v7 + 216)) / v10;
    else
      *v8 = 300;
    return 0;
  }
}

```

## disassembly

```asm
0x18000fb80  push    rbx
0x18000fb82  sub     rsp, 20h
0x18000fb86  mov     rax, [rsp+28h+arg_20]
0x18000fb8b  mov     r11, r9
0x18000fb8e  mov     ebx, r8d
0x18000fb91  mov     r10, rcx
0x18000fb94  cmp     dword ptr [rax], 4
0x18000fb97  jz      short loc_18000FBA4
0x18000fb99  mov     eax, 80070057h
0x18000fb9e  add     rsp, 20h
0x18000fba2  pop     rbx
0x18000fba3  retn
0x18000fba4  cmp     qword ptr [rcx+18h], 0
0x18000fba9  jz      loc_18000FC45
0x18000fbaf  lea     rdx, [rcx+54h]; struct tWAVEFORMATEX *
0x18000fbb3  call    ?IsValidFormat@CDSLink@@AEAAHPEBUtWAVEFORMATEX@@@Z; CDSLink::IsValidFormat(tWAVEFORMATEX const *)
0x18000fbb8  test    eax, eax
0x18000fbba  jz      loc_18000FC45
0x18000fbc0  test    ebx, ebx
0x18000fbc2  jz      short loc_18000FC0A
0x18000fbc4  mov     edx, [r11]
0x18000fbc7  cmp     edx, 5
0x18000fbca  jnb     short loc_18000FBD3
0x18000fbcc  mov     edx, 5
0x18000fbd1  jmp     short loc_18000FBDD
0x18000fbd3  mov     eax, 3E8h
0x18000fbd8  cmp     edx, eax
0x18000fbda  cmova   edx, eax
0x18000fbdd  imul    edx, [r10+5Ch]
0x18000fbe2  mov     eax, 10624DD3h
0x18000fbe7  movzx   ecx, word ptr [r10+56h]
0x18000fbec  add     edx, 1F4h
0x18000fbf2  mul     edx
0x18000fbf4  shr     edx, 6
0x18000fbf7  shr     edx, cl
0x18000fbf9  shl     edx, cl
0x18000fbfb  mov     [r10+0D8h], edx
0x18000fc02  xor     eax, eax
0x18000fc04  add     rsp, 20h
0x18000fc08  pop     rbx
0x18000fc09  retn
0x18000fc0a  mov     r8d, [r10+5Ch]
0x18000fc0e  test    r8d, r8d
0x18000fc11  jz      short loc_18000FC35
0x18000fc13  imul    eax, [r10+0D8h], 3E8h
0x18000fc1e  xor     edx, edx
0x18000fc20  mov     ecx, r8d
0x18000fc23  shr     ecx, 1
0x18000fc25  add     eax, ecx
0x18000fc27  div     r8d
0x18000fc2a  mov     [r11], eax
0x18000fc2d  xor     eax, eax
0x18000fc2f  add     rsp, 20h
0x18000fc33  pop     rbx
0x18000fc34  retn
0x18000fc35  mov     eax, 12Ch
0x18000fc3a  mov     [r11], eax
0x18000fc3d  xor     eax, eax
0x18000fc3f  add     rsp, 20h
0x18000fc43  pop     rbx
0x18000fc44  retn
0x18000fc45  mov     eax, 88781131h
0x18000fc4a  add     rsp, 20h
0x18000fc4e  pop     rbx
0x18000fc4f  retn
```
