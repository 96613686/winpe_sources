# PROTOCOL::RealReceiveCompletion(ulong,ulong)

- ea: `0x1800036b8`
- end: `0x180003908`
- name: `?RealReceiveCompletion@PROTOCOL@@AEAAJKK@Z`
- size: `592`
- prototype: `__int64 __fastcall(struct FCGI_BUFFER **this, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180003910`

## callees

- `0x180001e7c`
- `0x1800035f8`
- `0x1800036b8`
- `0x180003c08`
- `0x180008f90`
- `0x180009128`
- `0x18000edc6`

## pseudocode

```c
__int64 __fastcall PROTOCOL::RealReceiveCompletion(struct FCGI_BUFFER **this, int a2, int a3)
{
  int v3; // ebx
  bool v5; // cc
  int v6; // r12d
  int v7; // r15d
  struct _LIST_ENTRY *Flink; // rbx
  struct _LIST_ENTRY *v9; // rax
  struct _LIST_ENTRY *v10; // rbx
  struct _LIST_ENTRY *v11; // rdx
  int v12; // ecx
  unsigned int Blink; // eax
  int v14; // r14d
  int v15; // eax
  int v16; // ecx
  void **v17; // rax
  void **v18; // rsi
  int v19; // edx
  int *v20; // r9
  struct _LIST_ENTRY *v21; // rcx
  struct _LIST_ENTRY *v22; // rax
  struct _LIST_ENTRY v24; // [rsp+20h] [rbp-10h] BYREF
  int v25; // [rsp+70h] [rbp+40h] BYREF

  v25 = 0;
  v24.Blink = &v24;
  v24.Flink = &v24;
  v3 = a2;
  if ( a3 )
  {
    v5 = a2 <= 0;
    if ( !a2 )
    {
      v6 = 1;
      v7 = 0;
      v3 = PROTOCOL::SplitMessages((PROTOCOL *)this, this[15], a3, &v24);
      if ( v3 < 0 )
        goto LABEL_41;
      while ( 1 )
      {
        Flink = v24.Flink;
        if ( v24.Flink == &v24 )
        {
          v3 = PROTOCOL::PendReceive((PROTOCOL *)this);
          goto LABEL_41;
        }
        if ( v24.Flink->Blink != &v24 )
          goto LABEL_45;
        v9 = v24.Flink->Flink;
        if ( v24.Flink->Flink->Blink != v24.Flink )
          goto LABEL_45;
        v24.Flink = v24.Flink->Flink;
        v9->Blink = &v24;
        v10 = Flink - 2;
        v11 = v10->Flink;
        v12 = 0;
        if ( v24.Flink != &v24 )
          v12 = v6;
        v6 = v12;
        if ( BYTE1(v11->Flink) == 6 )
        {
          if ( !LODWORD(v10[1].Blink) )
            *((_DWORD *)this + 12) = 2;
          Blink = (unsigned int)v10->Blink;
          if ( *((_DWORD *)this + 34) < Blink )
            *((_DWORD *)this + 34) = Blink;
        }
        if ( BYTE1(v11->Flink) == 3 )
        {
          v7 = 1;
          *((_DWORD *)this + 12) = 4;
        }
        v14 = v12;
        switch ( BYTE1(v11->Flink) )
        {
          case 3:
            v15 = 6;
            v14 = 1;
            break;
          case 6:
          case 7:
            if ( !LODWORD(v10[1].Blink) )
            {
              FCGI_BUFFER::Free((FCGI_BUFFER *)v10);
              v3 = 0;
              goto LABEL_34;
            }
            v15 = (BYTE1(v11->Flink) != 6) + 4;
            break;
          case 0xA:
            v15 = 7;
            break;
          default:
            FCGI_BUFFER::Free((FCGI_BUFFER *)v10);
            v3 = -2147024883;
LABEL_33:
            if ( !v7 )
              goto LABEL_41;
            goto LABEL_34;
        }
        HIDWORD(v10[1].Blink) = v15;
        if ( LODWORD(v10->Blink) > 0x400 )
        {
          v16 = (int)v10[1].Blink;
          if ( (unsigned int)(10 * v16) < LODWORD(v10->Blink) )
          {
            v17 = (void **)FCGI_BUFFER::Alloc(v16);
            v18 = v17;
            if ( v17 )
            {
              memcpy_0(*v17, v10[1].Flink, LODWORD(v10[1].Blink));
              *((_DWORD *)v18 + 7) = HIDWORD(v10[1].Blink);
              v19 = (int)v10[1].Blink;
              v18[2] = *v18;
              *((_DWORD *)v18 + 6) = v19;
              FCGI_BUFFER::Free((FCGI_BUFFER *)v10);
              v10 = (struct _LIST_ENTRY *)v18;
            }
          }
        }
        v20 = &v25;
        if ( v14 )
          v20 = 0;
        v3 = SEND_QUEUE::Enqueue(this[23], (struct FCGI_BUFFER *)v10, v14, v20);
        if ( v3 < 0 )
          goto LABEL_33;
LABEL_34:
        if ( v25 || v7 )
          goto LABEL_41;
      }
    }
  }
  else
  {
    v5 = a2 <= 0;
  }
  if ( !v5 )
    v3 = (unsigned __int16)a2 | 0x80070000;
LABEL_41:
  while ( 1 )
  {
    v21 = v24.Flink;
    if ( v24.Flink == &v24 )
      break;
    if ( v24.Flink->Blink != &v24 || (v22 = v24.Flink->Flink, v24.Flink->Flink->Blink != v24.Flink) )
LABEL_45:
      __fastfail(3u);
    v24.Flink = v24.Flink->Flink;
    v22->Blink = &v24;
    FCGI_BUFFER::Free((FCGI_BUFFER *)&v21[-2]);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800036b8  mov     [rsp-28h+arg_0], rbx
0x1800036bd  mov     [rsp-28h+arg_8], rsi
0x1800036c2  push    rbp
0x1800036c3  push    rdi
0x1800036c4  push    r12
0x1800036c6  push    r14
0x1800036c8  push    r15
0x1800036ca  mov     rbp, rsp
0x1800036cd  sub     rsp, 30h
0x1800036d1  mov     [rbp+arg_10], 0
0x1800036d8  lea     rax, [rbp+var_10]
0x1800036dc  mov     [rbp+var_10.Blink], rax
0x1800036e0  lea     rax, [rbp+var_10]
0x1800036e4  mov     [rbp+var_10.Flink], rax
0x1800036e8  mov     ebx, edx
0x1800036ea  mov     rdi, rcx
0x1800036ed  test    r8d, r8d
0x1800036f0  jz      loc_1800038A4
0x1800036f6  test    edx, edx
0x1800036f8  jnz     loc_1800038A6
0x1800036fe  lea     r12d, [rdx+1]
0x180003702  xor     r15d, r15d
0x180003705  mov     rdx, [rcx+78h]; struct FCGI_BUFFER *
0x180003709  lea     r9, [rbp+var_10]; struct _LIST_ENTRY *
0x18000370d  call    ?SplitMessages@PROTOCOL@@AEAAJPEAVFCGI_BUFFER@@KPEAU_LIST_ENTRY@@@Z; PROTOCOL::SplitMessages(FCGI_BUFFER *,ulong,_LIST_ENTRY *)
0x180003712  mov     ebx, eax
0x180003714  test    eax, eax
0x180003716  js      loc_1800038B1
0x18000371c  mov     rbx, [rbp+var_10.Flink]
0x180003720  lea     rax, [rbp+var_10]
0x180003724  cmp     rbx, rax
0x180003727  jz      loc_180003898
0x18000372d  lea     rax, [rbp+var_10]
0x180003731  cmp     [rbx+8], rax
0x180003735  jnz     loc_1800038E8
0x18000373b  mov     rax, [rbx]
0x18000373e  cmp     [rax+8], rbx
0x180003742  jnz     loc_1800038E8
0x180003748  mov     [rbp+var_10.Flink], rax
0x18000374c  lea     rcx, [rbp+var_10]
0x180003750  mov     [rax+8], rcx
0x180003754  add     rbx, 0FFFFFFFFFFFFFFE0h
0x180003758  lea     rax, [rbp+var_10]
0x18000375c  cmp     [rbp+var_10.Flink], rax
0x180003760  mov     rdx, [rbx]
0x180003763  setz    al
0x180003766  xor     ecx, ecx
0x180003768  test    al, al
0x18000376a  cmovz   ecx, r12d
0x18000376e  cmp     byte ptr [rdx+1], 6
0x180003772  mov     r12d, ecx
0x180003775  jnz     short loc_180003795
0x180003777  cmp     dword ptr [rbx+18h], 0
0x18000377b  jnz     short loc_180003784
0x18000377d  mov     dword ptr [rdi+30h], 2
0x180003784  mov     eax, [rbx+8]
0x180003787  cmp     [rdi+88h], eax
0x18000378d  jnb     short loc_180003795
0x18000378f  mov     [rdi+88h], eax
0x180003795  cmp     byte ptr [rdx+1], 3
0x180003799  jnz     short loc_1800037A8
0x18000379b  mov     r15d, 1
0x1800037a1  mov     dword ptr [rdi+30h], 4
0x1800037a8  mov     r14d, ecx
0x1800037ab  movzx   ecx, byte ptr [rdx+1]
0x1800037af  mov     eax, ecx
0x1800037b1  sub     eax, 3
0x1800037b4  jz      short loc_180003800
0x1800037b6  sub     eax, 3
0x1800037b9  jz      short loc_1800037DE
0x1800037bb  sub     eax, 1
0x1800037be  jz      short loc_1800037DE
0x1800037c0  cmp     eax, 3
0x1800037c3  jz      short loc_1800037D7
0x1800037c5  mov     rcx, rbx; this
0x1800037c8  call    ?Free@FCGI_BUFFER@@QEAAJXZ; FCGI_BUFFER::Free(void)
0x1800037cd  mov     ebx, 8007000Dh
0x1800037d2  jmp     loc_180003882
0x1800037d7  mov     eax, 7
0x1800037dc  jmp     short loc_180003809
0x1800037de  cmp     dword ptr [rbx+18h], 0
0x1800037e2  jnz     short loc_1800037F3
0x1800037e4  mov     rcx, rbx; this
0x1800037e7  call    ?Free@FCGI_BUFFER@@QEAAJXZ; FCGI_BUFFER::Free(void)
0x1800037ec  xor     ebx, ebx
0x1800037ee  jmp     loc_180003887
0x1800037f3  xor     eax, eax
0x1800037f5  cmp     cl, 6
0x1800037f8  setnz   al
0x1800037fb  add     eax, 4
0x1800037fe  jmp     short loc_180003809
0x180003800  mov     eax, 6
0x180003805  lea     r14d, [rax-5]
0x180003809  mov     [rbx+1Ch], eax
0x18000380c  cmp     dword ptr [rbx+8], 400h
0x180003813  jbe     short loc_18000385D
0x180003815  mov     ecx, [rbx+18h]; unsigned int
0x180003818  lea     eax, [rcx+rcx*4]
0x18000381b  add     eax, eax
0x18000381d  cmp     eax, [rbx+8]
0x180003820  jnb     short loc_18000385D
0x180003822  call    ?Alloc@FCGI_BUFFER@@SAPEAV1@K@Z; FCGI_BUFFER::Alloc(ulong)
0x180003827  mov     rsi, rax
0x18000382a  test    rax, rax
0x18000382d  jz      short loc_18000385D
0x18000382f  mov     r8d, [rbx+18h]; Size
0x180003833  mov     rdx, [rbx+10h]; Src
0x180003837  mov     rcx, [rax]; void *
0x18000383a  call    memcpy_0
0x18000383f  mov     ecx, [rbx+1Ch]
0x180003842  mov     [rsi+1Ch], ecx
0x180003845  mov     rcx, [rsi]
0x180003848  mov     edx, [rbx+18h]
0x18000384b  mov     [rsi+10h], rcx
0x18000384f  mov     rcx, rbx; this
0x180003852  mov     [rsi+18h], edx
0x180003855  call    ?Free@FCGI_BUFFER@@QEAAJXZ; FCGI_BUFFER::Free(void)
0x18000385a  mov     rbx, rsi
0x18000385d  mov     rcx, [rdi+0B8h]; this
0x180003864  lea     r9, [rbp+arg_10]
0x180003868  xor     eax, eax
0x18000386a  mov     r8d, r14d; int
0x18000386d  test    r14d, r14d
0x180003870  mov     rdx, rbx; struct FCGI_BUFFER *
0x180003873  cmovnz  r9, rax; int *
0x180003877  call    ?Enqueue@SEND_QUEUE@@QEAAJPEAVFCGI_BUFFER@@HPEAH@Z; SEND_QUEUE::Enqueue(FCGI_BUFFER *,int,int *)
0x18000387c  mov     ebx, eax
0x18000387e  test    eax, eax
0x180003880  jns     short loc_180003887
0x180003882  test    r15d, r15d
0x180003885  jz      short loc_1800038B1
0x180003887  cmp     [rbp+arg_10], 0
0x18000388b  jnz     short loc_1800038B1
0x18000388d  test    r15d, r15d
0x180003890  jz      loc_18000371C
0x180003896  jmp     short loc_1800038B1
0x180003898  mov     rcx, rdi; this
0x18000389b  call    ?PendReceive@PROTOCOL@@AEAAJXZ; PROTOCOL::PendReceive(void)
0x1800038a0  mov     ebx, eax
0x1800038a2  jmp     short loc_1800038B1
0x1800038a4  test    edx, edx
0x1800038a6  jle     short loc_1800038B1
0x1800038a8  movzx   ebx, dx
0x1800038ab  or      ebx, 80070000h
0x1800038b1  mov     rcx, [rbp+var_10.Flink]
0x1800038b5  lea     rax, [rbp+var_10]
0x1800038b9  cmp     rcx, rax
0x1800038bc  jz      short loc_1800038EF
0x1800038be  lea     rax, [rbp+var_10]
0x1800038c2  cmp     [rcx+8], rax
0x1800038c6  jnz     short loc_1800038E8
0x1800038c8  mov     rax, [rcx]
0x1800038cb  cmp     [rax+8], rcx
0x1800038cf  jnz     short loc_1800038E8
0x1800038d1  lea     rdx, [rbp+var_10]
0x1800038d5  mov     [rbp+var_10.Flink], rax
0x1800038d9  add     rcx, 0FFFFFFFFFFFFFFE0h; this
0x1800038dd  mov     [rax+8], rdx
0x1800038e1  call    ?Free@FCGI_BUFFER@@QEAAJXZ; FCGI_BUFFER::Free(void)
0x1800038e6  jmp     short loc_1800038B1
0x1800038e8  mov     ecx, 3
0x1800038ed  int     29h; Win8: RtlFailFast(ecx)
0x1800038ef  mov     rsi, [rsp+30h+arg_8]
0x1800038f4  mov     eax, ebx
0x1800038f6  mov     rbx, [rsp+30h+arg_0]
0x1800038fb  add     rsp, 30h
0x1800038ff  pop     r15
0x180003901  pop     r14
0x180003903  pop     r12
0x180003905  pop     rdi
0x180003906  pop     rbp
0x180003907  retn
```
