# CUserHeader::GetQueue(uchar const *,bool,ulong,QUEUE_FORMAT *)

- ea: `0x140002534`
- end: `0x140002647`
- name: `?GetQueue@CUserHeader@@AEBAHPEBE_NKPEAUQUEUE_FORMAT@@@Z`
- size: `275`
- prototype: `__int64 __fastcall(CUserHeader *__hidden this, const unsigned __int8 *, bool, unsigned int, struct QUEUE_FORMAT *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140002238`
- `0x140002650`
- `0x140014ef8`
- `0x140015e04`
- `0x14001757c`

## callees

- `0x140002238`
- `0x140002534`

## pseudocode

```c
__int64 __fastcall CUserHeader::GetQueue(
        CUserHeader *this,
        const unsigned __int8 *a2,
        char a3,
        int a4,
        struct QUEUE_FORMAT *a5)
{
  int v7; // r9d
  int v8; // r9d
  int v9; // r9d
  int v10; // r9d
  int v11; // r9d
  int v12; // r9d
  struct QUEUE_FORMAT *v13; // rcx
  const unsigned __int8 *v14; // rax
  struct QUEUE_FORMAT *v15; // rax
  int v16; // ecx
  __int128 v17; // xmm0
  int v18; // eax
  __int128 v19; // xmm0

  if ( a4 )
  {
    v7 = a4 - 1;
    if ( !v7 )
      return CUserHeader::GetAdminQueue(this, a5);
    v8 = v7 - 1;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          v11 = v10 - 1;
          if ( v11 )
          {
            v12 = v11 - 1;
            if ( v12 )
            {
              if ( v12 == 1 )
              {
                v13 = a5;
                v14 = a2 + 2;
                *(_WORD *)a5 = 3;
LABEL_19:
                *((_QWORD *)v13 + 1) = v14;
                return 1;
              }
              return 0;
            }
            v15 = a5;
            v16 = *((_DWORD *)a2 + 4);
            *(_WORD *)a5 = 2;
            v17 = *(_OWORD *)a2;
            goto LABEL_15;
          }
          *(_WORD *)a5 = 1;
          *(_OWORD *)((char *)a5 + 8) = *(_OWORD *)a2;
        }
        else
        {
          CUserHeader::GetAdminQueue(this, a5);
          v18 = *(_DWORD *)a2;
          *(_WORD *)a5 = 2;
          v19 = *(_OWORD *)((char *)a5 + 8);
          *((_DWORD *)a5 + 6) = v18;
          *(_OWORD *)((char *)a5 + 8) = v19;
        }
        return 1;
      }
      v15 = a5;
      v16 = *(_DWORD *)a2;
      *(_WORD *)a5 = 2;
      v17 = *((_OWORD *)this + 1);
    }
    else
    {
      v15 = a5;
      v16 = *(_DWORD *)a2;
      *(_WORD *)a5 = 2;
      v17 = *(_OWORD *)this;
    }
LABEL_15:
    *(_OWORD *)((char *)v15 + 8) = v17;
    *((_DWORD *)v15 + 6) = v16;
    return 1;
  }
  v13 = a5;
  if ( a3 )
  {
    v14 = *(const unsigned __int8 **)a2;
    *(_WORD *)a5 = 7;
    goto LABEL_19;
  }
  *(_WORD *)a5 = 0;
  return 0;
}

```

## disassembly

```asm
0x140002534  mov     [rsp+arg_0], rbx
0x140002539  push    rdi
0x14000253a  sub     rsp, 20h
0x14000253e  mov     rdi, rdx
0x140002541  mov     r10, rcx
0x140002544  test    r9d, r9d
0x140002547  jz      loc_140002617
0x14000254d  sub     r9d, 1
0x140002551  jz      loc_14000260B
0x140002557  sub     r9d, 1
0x14000255b  jz      loc_1400025F1
0x140002561  sub     r9d, 1
0x140002565  jz      short loc_1400025DE
0x140002567  sub     r9d, 1
0x14000256b  jz      short loc_1400025BC
0x14000256d  sub     r9d, 1
0x140002571  jz      short loc_1400025A8
0x140002573  sub     r9d, 1
0x140002577  jz      short loc_140002596
0x140002579  cmp     r9d, 1
0x14000257d  jnz     loc_140002639
0x140002583  mov     rcx, [rsp+28h+arg_20]
0x140002588  lea     rax, [rdx+2]
0x14000258c  mov     word ptr [rcx], 3
0x140002591  jmp     loc_140002629
0x140002596  mov     rax, [rsp+28h+arg_20]
0x14000259b  mov     ecx, [rdx+10h]; this
0x14000259e  mov     word ptr [rax], 2
0x1400025a3  movups  xmm0, xmmword ptr [rdx]
0x1400025a6  jmp     short loc_140002601
0x1400025a8  mov     rax, [rsp+28h+arg_20]
0x1400025ad  mov     word ptr [rax], 1
0x1400025b2  movups  xmm0, xmmword ptr [rdx]
0x1400025b5  movdqu  xmmword ptr [rax+8], xmm0
0x1400025ba  jmp     short loc_14000262D
0x1400025bc  mov     rbx, [rsp+28h+arg_20]
0x1400025c1  mov     rdx, rbx; struct QUEUE_FORMAT *
0x1400025c4  call    ?GetAdminQueue@CUserHeader@@QEBAHPEAUQUEUE_FORMAT@@@Z; CUserHeader::GetAdminQueue(QUEUE_FORMAT *)
0x1400025c9  mov     eax, [rdi]
0x1400025cb  mov     word ptr [rbx], 2
0x1400025d0  movups  xmm0, xmmword ptr [rbx+8]
0x1400025d4  mov     [rbx+18h], eax
0x1400025d7  movdqu  xmmword ptr [rbx+8], xmm0
0x1400025dc  jmp     short loc_14000262D
0x1400025de  mov     rax, [rsp+28h+arg_20]
0x1400025e3  mov     ecx, [rdx]
0x1400025e5  mov     word ptr [rax], 2
0x1400025ea  movups  xmm0, xmmword ptr [r10+10h]
0x1400025ef  jmp     short loc_140002601
0x1400025f1  mov     rax, [rsp+28h+arg_20]
0x1400025f6  mov     ecx, [rdx]; this
0x1400025f8  mov     word ptr [rax], 2
0x1400025fd  movups  xmm0, xmmword ptr [r10]
0x140002601  movdqu  xmmword ptr [rax+8], xmm0
0x140002606  mov     [rax+18h], ecx
0x140002609  jmp     short loc_14000262D
0x14000260b  mov     rdx, [rsp+28h+arg_20]; struct QUEUE_FORMAT *
0x140002610  call    ?GetAdminQueue@CUserHeader@@QEBAHPEAUQUEUE_FORMAT@@@Z; CUserHeader::GetAdminQueue(QUEUE_FORMAT *)
0x140002615  jmp     short loc_14000263B
0x140002617  mov     rcx, [rsp+28h+arg_20]
0x14000261c  test    r8b, r8b
0x14000261f  jz      short loc_140002634
0x140002621  mov     rax, [rdx]
0x140002624  mov     word ptr [rcx], 7
0x140002629  mov     [rcx+8], rax
0x14000262d  mov     eax, 1
0x140002632  jmp     short loc_14000263B
0x140002634  mov     word ptr [rcx], 0
0x140002639  xor     eax, eax
0x14000263b  mov     rbx, [rsp+28h+arg_0]
0x140002640  add     rsp, 20h
0x140002644  pop     rdi
0x140002645  retn
```
