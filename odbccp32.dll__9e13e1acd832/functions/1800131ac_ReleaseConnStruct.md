# ReleaseConnStruct

- ea: `0x1800131ac`
- end: `0x180013267`
- name: `ReleaseConnStruct`
- size: `187`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000295c`
- `0x180004580`
- `0x18001217c`

## callees

- `0x180002940`
- `0x1800131ac`

## pseudocode

```c
__int64 __fastcall ReleaseConnStruct(__int64 a1)
{
  _BYTE *v2; // rax
  __int64 v3; // rcx
  __int64 i; // rcx
  void **j; // rcx
  void **v6; // rdi

  if ( a1 )
  {
    OFree(*(void **)(a1 + 8));
    OFree(*(void **)(a1 + 16));
    OFree(*(void **)(a1 + 24));
    OFree(*(void **)(a1 + 32));
    OFree(*(void **)(a1 + 40));
    v2 = *(_BYTE **)(a1 + 48);
    if ( !v2 )
      goto LABEL_10;
    v3 = -1;
    do
      ++v3;
    while ( *(_WORD *)&v2[2 * v3] );
    for ( i = 2 * v3; i; --i )
      *v2++ = 0;
    for ( j = *(void ***)(a1 + 48); ; j = v6 )
    {
      OFree(j);
LABEL_10:
      v6 = *(void ***)(a1 + 72);
      if ( !v6 )
        break;
      *(_QWORD *)(a1 + 72) = v6[2];
      OFree(*v6);
      OFree(v6[1]);
    }
    OFree((void *)a1);
  }
  return 0;
}

```

## disassembly

```asm
0x1800131ac  mov     [rsp+arg_0], rbx
0x1800131b1  mov     [rsp+arg_8], rsi
0x1800131b6  push    rdi
0x1800131b7  sub     rsp, 20h
0x1800131bb  xor     esi, esi
0x1800131bd  mov     rbx, rcx
0x1800131c0  test    rcx, rcx
0x1800131c3  jz      loc_180013255
0x1800131c9  mov     rcx, [rcx+8]
0x1800131cd  call    OFree
0x1800131d2  mov     rcx, [rbx+10h]
0x1800131d6  call    OFree
0x1800131db  mov     rcx, [rbx+18h]
0x1800131df  call    OFree
0x1800131e4  mov     rcx, [rbx+20h]
0x1800131e8  call    OFree
0x1800131ed  mov     rcx, [rbx+28h]
0x1800131f1  call    OFree
0x1800131f6  mov     rax, [rbx+30h]
0x1800131fa  test    rax, rax
0x1800131fd  jz      short loc_180013244
0x1800131ff  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180013203  inc     rcx
0x180013206  cmp     [rax+rcx*2], si
0x18001320a  jnz     short loc_180013203
0x18001320c  add     rcx, rcx
0x18001320f  jz      short loc_18001321D
0x180013211  mov     [rax], sil
0x180013214  inc     rax
0x180013217  sub     rcx, 1
0x18001321b  jnz     short loc_180013211
0x18001321d  mov     rcx, [rbx+30h]
0x180013221  jmp     short loc_18001323F
0x180013223  mov     rax, [rdi+10h]
0x180013227  mov     [rbx+48h], rax
0x18001322b  mov     rcx, [rdi]
0x18001322e  call    OFree
0x180013233  mov     rcx, [rdi+8]
0x180013237  call    OFree
0x18001323c  mov     rcx, rdi
0x18001323f  call    OFree
0x180013244  mov     rdi, [rbx+48h]
0x180013248  test    rdi, rdi
0x18001324b  jnz     short loc_180013223
0x18001324d  mov     rcx, rbx
0x180013250  call    OFree
0x180013255  mov     rbx, [rsp+28h+arg_0]
0x18001325a  mov     eax, esi
0x18001325c  mov     rsi, [rsp+28h+arg_8]
0x180013261  add     rsp, 20h
0x180013265  pop     rdi
0x180013266  retn
```
