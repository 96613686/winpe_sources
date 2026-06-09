# FveBcdUtil::IsAssociatedOS(void *,_GUID *,_GUID *,uchar *)

- ea: `0x1800137d8`
- end: `0x1800138ce`
- name: `?IsAssociatedOS@FveBcdUtil@@SAJPEAXPEAU_GUID@@1PEAE@Z`
- size: `246`
- prototype: `__int64 __fastcall(void *, struct _GUID *, struct _GUID *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800126b8`

## callees

- `0x1800022d8`
- `0x18000ff64`
- `0x1800129dc`
- `0x1800137d8`

## import_xrefs

- `bcd!BcdOpenObject` at `0x18001380d`
- `bcd!BcdOpenObject` at `0x18001380d`
- `bcd!BcdCloseObject` at `0x1800138b6`
- `bcd!BcdCloseObject` at `0x18002c8f9`
- `bcd!BcdCloseObject` at `0x1800138b6`
- `bcd!BcdCloseObject` at `0x18002c8f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FveBcdUtil::IsAssociatedOS(void *a1, struct _GUID *a2, struct _GUID *a3, unsigned __int8 *a4)
{
  NTSTATUS v6; // eax
  signed int v7; // ebx
  int BcdElementData; // eax
  unsigned int i; // eax
  _QWORD *v10; // r8
  __int64 v11; // rdx
  void *Block; // [rsp+28h] [rbp-20h] BYREF
  void *v14; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v15; // [rsp+68h] [rbp+20h] BYREF

  v14 = 0;
  Block = 0;
  v15 = 0;
  *a4 = 0;
  v6 = BcdOpenObject(a1, a2, &v14);
  v7 = FromNtStatus(v6);
  if ( v7 >= 0 )
  {
    BcdElementData = FveBcdUtil::GetBcdElementData(v14, 0x14000008u, &Block, &v15);
    v7 = BcdElementData;
    if ( BcdElementData >= 0 )
    {
      if ( (v15 & 0xF) != 0 )
      {
        v7 = -2147024809;
      }
      else
      {
        for ( i = 0; i < v15 >> 4; ++i )
        {
          v10 = (char *)Block + 16 * i;
          v11 = *(_QWORD *)&a3->Data1 - *v10;
          if ( *(_QWORD *)&a3->Data1 == *v10 )
            v11 = *(_QWORD *)a3->Data4 - v10[1];
          if ( !v11 )
          {
            *a4 = 1;
            break;
          }
        }
      }
    }
    else if ( BcdElementData == -2147023728 )
    {
      v7 = 0;
    }
  }
  if ( Block )
    operator delete(Block);
  if ( v14 )
    BcdCloseObject(v14);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800137d8  mov     rax, rsp
0x1800137db  mov     [rax+8], rbx
0x1800137df  mov     [rax+10h], rsi
0x1800137e3  push    rdi
0x1800137e4  sub     rsp, 40h
0x1800137e8  mov     rdi, r9
0x1800137eb  mov     rsi, r8
0x1800137ee  mov     qword ptr [rax-18h], 0
0x1800137f6  mov     qword ptr [rax-20h], 0
0x1800137fe  mov     dword ptr [rax+20h], 0
0x180013805  mov     byte ptr [r9], 0
0x180013809  lea     r8, [rax-18h]
0x18001380d  call    cs:__imp_BcdOpenObject
0x180013813  mov     ecx, eax; int
0x180013815  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18001381a  mov     ebx, eax
0x18001381c  mov     [rsp+48h+var_28], eax
0x180013820  test    eax, eax
0x180013822  js      short loc_18001389D
0x180013824  lea     r9, [rsp+48h+arg_18]; unsigned int *
0x180013829  lea     r8, [rsp+48h+Block]; void **
0x18001382e  mov     edx, 14000008h; unsigned int
0x180013833  mov     rcx, [rsp+48h+var_18]; void *
0x180013838  call    ?GetBcdElementData@FveBcdUtil@@SAJPEAXKPEAPEAXPEAK@Z; FveBcdUtil::GetBcdElementData(void *,ulong,void * *,ulong *)
0x18001383d  mov     ebx, eax
0x18001383f  mov     [rsp+48h+var_28], eax
0x180013843  test    eax, eax
0x180013845  jns     short loc_180013856
0x180013847  cmp     eax, 80070490h
0x18001384c  jnz     short loc_18001389D
0x18001384e  xor     ebx, ebx
0x180013850  mov     [rsp+48h+var_28], ebx
0x180013854  jmp     short loc_18001389D
0x180013856  mov     ecx, [rsp+48h+arg_18]
0x18001385a  test    cl, 0Fh
0x18001385d  jz      short loc_180013866
0x18001385f  mov     ebx, 80070057h
0x180013864  jmp     short loc_180013850
0x180013866  shr     ecx, 4
0x180013869  xor     eax, eax
0x18001386b  mov     [rsp+48h+var_24], eax
0x18001386f  cmp     eax, ecx
0x180013871  jnb     short loc_18001389D
0x180013873  mov     r8d, eax
0x180013876  shl     r8, 4
0x18001387a  add     r8, [rsp+48h+Block]
0x18001387f  mov     rdx, [rsi]
0x180013882  sub     rdx, [r8]
0x180013885  jnz     short loc_18001388F
0x180013887  mov     rdx, [rsi+8]
0x18001388b  sub     rdx, [r8+8]
0x18001388f  test    rdx, rdx
0x180013892  jnz     short loc_180013899
0x180013894  mov     byte ptr [rdi], 1
0x180013897  jmp     short loc_18001389D
0x180013899  inc     eax
0x18001389b  jmp     short loc_18001386B
0x18001389d  mov     rcx, [rsp+48h+Block]; Block
0x1800138a2  test    rcx, rcx
0x1800138a5  jz      short loc_1800138AC
0x1800138a7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800138ac  mov     rcx, [rsp+48h+var_18]
0x1800138b1  test    rcx, rcx
0x1800138b4  jz      short loc_1800138BC
0x1800138b6  call    cs:__imp_BcdCloseObject
0x1800138bc  mov     eax, ebx
0x1800138be  mov     rbx, [rsp+48h+arg_0]
0x1800138c3  mov     rsi, [rsp+48h+arg_8]
0x1800138c8  add     rsp, 40h
0x1800138cc  pop     rdi
0x1800138cd  retn
0x18002c8d8  push    rbp
0x18002c8da  sub     rsp, 20h
0x18002c8de  mov     rbp, rdx
0x18002c8e1  mov     rcx, [rbp+28h]; Block
0x18002c8e5  test    rcx, rcx
0x18002c8e8  jz      short loc_18002C8F0
0x18002c8ea  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c8ef  nop
0x18002c8f0  mov     rcx, [rbp+30h]
0x18002c8f4  test    rcx, rcx
0x18002c8f7  jz      short loc_18002C900
0x18002c8f9  call    cs:__imp_BcdCloseObject
0x18002c8ff  nop
0x18002c900  add     rsp, 20h
0x18002c904  pop     rbp
0x18002c905  retn
```
