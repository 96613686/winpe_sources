# Instance::CreateTable(ushort const *,ulong,ulong,Err &)

- ea: `0x10035f50`
- end: `0x10036152`
- name: `?CreateTable@Instance@@QAEPAVCursor@@PBGKKAAVErr@@@Z`
- size: `514`
- prototype: `struct Cursor *__thiscall(Instance *__hidden this, const unsigned __int16 *Src, unsigned int, unsigned int, struct Err *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops`

## callers

- `0x100289a0`

## callees

- `0x1000eb60`
- `0x1000f750`
- `0x10019240`
- `0x10025ee0`
- `0x10035f50`
- `0x100518a0`
- `0x10051e80`
- `0x10052140`
- `0x10052e30`
- `0x10053950`
- `0x10053f40`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e798`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
struct Cursor *__thiscall Instance::CreateTable(
        Instance *this,
        unsigned __int16 *Src,
        unsigned int a3,
        unsigned int a4,
        void **a5)
{
  int v6; // eax
  int v7; // eax
  int v8; // ecx
  Table *v9; // edi
  struct Err *v10; // ecx
  int v11; // ecx
  unsigned int v13; // [esp-Ch] [ebp-44h]
  unsigned int v14; // [esp-8h] [ebp-40h]
  void *v15[3]; // [esp+10h] [ebp-28h] BYREF
  void *Block; // [esp+1Ch] [ebp-1Ch]
  void *v17; // [esp+20h] [ebp-18h]
  void *v18; // [esp+24h] [ebp-14h]
  void (__thiscall ***v19)(_DWORD, int); // [esp+28h] [ebp-10h]
  int v20; // [esp+34h] [ebp-4h]

  v6 = *((_DWORD *)this + 4);
  v19 = 0;
  v7 = *(_DWORD *)(v6 + 104);
  if ( (!v7 || v7 == 3) && (int)*a5 < 8 )
  {
    if ( ((unsigned int)*a5 & 0xFFFFFFFE) != 0 )
    {
      if ( a5[3] )
        operator delete[](a5[3]);
      if ( a5[4] )
        operator delete[](a5[4]);
    }
    *a5 = (void *)8;
    a5[1] = (void *)-1809;
    a5[2] = 0;
    a5[3] = 0;
    a5[4] = 0;
  }
  if ( (*(_BYTE *)a5 & 8) == 0 )
  {
    v18 = operator new(0x778u);
    v20 = 0;
    v9 = Table::Table((Table *)v18, *((struct Database **)this + 4), (struct Err *)a5);
    v20 = -1;
    if ( !v9 )
      Err::SetError(a5, -1011, v8);
    if ( (*(_BYTE *)a5 & 8) == 0 )
    {
      Table::Create(v9, (struct Transaction **)this, Src, v13, v14, (struct Err *)a5);
      if ( (*(_BYTE *)a5 & 8) != 0 )
      {
        if ( v9 )
        {
          Table::~Table(v9);
          operator delete(v9);
        }
      }
      else
      {
        Table::SetName(v9, Src, v10);
        v18 = operator new(0x16Cu);
        v19 = (void (__thiscall ***)(_DWORD, int))Cursor::Cursor(v18, this, v9, 2, 0, a5, 0);
        v20 = -1;
        if ( v19 )
        {
          if ( (*(_BYTE *)a5 & 8) != 0 )
          {
            v15[0] = (void *)1;
            v20 = 3;
            Table::Delete((struct Database **)v9, this, v15);
            (**v19)(v19, 1);
            v19 = 0;
            Err::~Err((Err *)v15);
          }
        }
        else
        {
          Err::SetError(a5, -1011, v11);
          ++*((_DWORD *)v9 + 19);
          v15[0] = (void *)1;
          v20 = 2;
          Table::Delete((struct Database **)v9, this, v15);
          Table::Release(v9, this);
          if ( ((int)v15[0] & 0xFFFFFFFE) != 0 )
          {
            if ( Block )
              operator delete[](Block);
            if ( v17 )
              operator delete[](v17);
          }
        }
      }
    }
  }
  return (struct Cursor *)v19;
}

```

## disassembly

```asm
0x10035f50  mov     edi, edi
0x10035f52  push    ebp
0x10035f53  mov     ebp, esp
0x10035f55  push    0FFFFFFFFh
0x10035f57  push    offset ?CreateTable@Instance@@QAEPAVCursor@@PBGKKAAVErr@@@Z_SEH
0x10035f5c  mov     eax, large fs:0
0x10035f62  push    eax
0x10035f63  sub     esp, 1Ch
0x10035f66  push    ebx
0x10035f67  push    esi
0x10035f68  push    edi
0x10035f69  mov     eax, ___security_cookie
0x10035f6e  xor     eax, ebp
0x10035f70  push    eax; unsigned int
0x10035f71  lea     eax, [ebp+var_C]
0x10035f74  mov     large fs:0, eax
0x10035f7a  mov     ebx, ecx
0x10035f7c  mov     eax, [ebx+10h]
0x10035f7f  xor     edi, edi
0x10035f81  mov     esi, [ebp+arg_C]
0x10035f84  mov     [ebp+var_10], edi
0x10035f87  mov     eax, [eax+68h]
0x10035f8a  test    eax, eax
0x10035f8c  jz      short loc_10035F93
0x10035f8e  cmp     eax, 3
0x10035f91  jnz     short loc_10035FD7
0x10035f93  mov     eax, [esi]
0x10035f95  cmp     eax, 8
0x10035f98  jge     short loc_10035FD7
0x10035f9a  test    eax, 0FFFFFFFEh
0x10035f9f  jz      short loc_10035FC1
0x10035fa1  mov     eax, [esi+0Ch]
0x10035fa4  test    eax, eax
0x10035fa6  jz      short loc_10035FB1
0x10035fa8  push    eax; Block
0x10035fa9  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10035fae  add     esp, 4
0x10035fb1  mov     eax, [esi+10h]
0x10035fb4  test    eax, eax
0x10035fb6  jz      short loc_10035FC1
0x10035fb8  push    eax; Block
0x10035fb9  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10035fbe  add     esp, 4
0x10035fc1  mov     dword ptr [esi], 8
0x10035fc7  mov     dword ptr [esi+4], 0FFFFF8EFh
0x10035fce  mov     [esi+8], edi
0x10035fd1  mov     [esi+0Ch], edi
0x10035fd4  mov     [esi+10h], edi
0x10035fd7  test    byte ptr [esi], 8
0x10035fda  jnz     loc_1003613B
0x10035fe0  push    778h; Size
0x10035fe5  call    ??2@YAPAXI@Z; operator new(uint)
0x10035fea  add     esp, 4
0x10035fed  mov     [ebp+var_14], eax
0x10035ff0  push    esi; struct Err *
0x10035ff1  mov     [ebp+var_4], 0
0x10035ff8  mov     ecx, eax; this
0x10035ffa  push    dword ptr [ebx+10h]; struct Database *
0x10035ffd  call    ??0Table@@QAE@PAVDatabase@@AAVErr@@@Z; Table::Table(Database *,Err &)
0x10036002  mov     edi, eax
0x10036004  mov     [ebp+var_4], 0FFFFFFFFh
0x1003600b  test    edi, edi
0x1003600d  jnz     short loc_1003601C
0x1003600f  push    ecx
0x10036010  push    0FFFFFC0Dh; unsigned int
0x10036015  mov     ecx, esi
0x10036017  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1003601c  test    byte ptr [esi], 8
0x1003601f  jnz     loc_1003613B
0x10036025  push    esi; struct Err *
0x10036026  sub     esp, 8
0x10036029  mov     ecx, edi; this
0x1003602b  push    [ebp+Src]; unsigned __int16 *
0x1003602e  push    ebx; struct Instance *
0x1003602f  call    ?Create@Table@@QAEXPAVInstance@@PBGKKAAVErr@@@Z; Table::Create(Instance *,ushort const *,ulong,ulong,Err &)
0x10036034  test    byte ptr [esi], 8
0x10036037  jz      short loc_1003605B
0x10036039  test    edi, edi
0x1003603b  jz      loc_1003613B
0x10036041  mov     ecx, edi; this
0x10036043  call    ??1Table@@QAE@XZ; Table::~Table(void)
0x10036048  push    778h; unsigned int
0x1003604d  push    edi; Block
0x1003604e  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x10036053  add     esp, 8
0x10036056  jmp     loc_1003613B
0x1003605b  push    ecx; struct Err *
0x1003605c  push    [ebp+Src]; Src
0x1003605f  mov     ecx, edi; this
0x10036061  call    ?SetName@Table@@QAEXPBGAAVErr@@@Z; Table::SetName(ushort const *,Err &)
0x10036066  push    16Ch; Size
0x1003606b  call    ??2@YAPAXI@Z; operator new(uint)
0x10036070  add     esp, 4
0x10036073  mov     [ebp+var_14], eax
0x10036076  push    0
0x10036078  push    esi
0x10036079  push    0
0x1003607b  push    2
0x1003607d  push    edi
0x1003607e  push    ebx
0x1003607f  mov     ecx, eax
0x10036081  mov     [ebp+var_4], 1
0x10036088  call    ??0Cursor@@QAE@PAVInstance@@PAVTable@@W4CurMode@@W4CurAcc@@AAVErr@@I@Z; Cursor::Cursor(Instance *,Table *,CurMode,CurAcc,Err &,uint)
0x1003608d  mov     [ebp+var_10], eax
0x10036090  mov     [ebp+var_4], 0FFFFFFFFh
0x10036097  test    eax, eax
0x10036099  jnz     short loc_100360F8
0x1003609b  push    ecx
0x1003609c  push    0FFFFFC0Dh
0x100360a1  mov     ecx, esi
0x100360a3  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x100360a8  inc     dword ptr [edi+4Ch]
0x100360ab  mov     [ebp+var_28], 1
0x100360b2  lea     eax, [ebp+var_28]
0x100360b5  mov     [ebp+var_4], 2
0x100360bc  push    eax; struct Err *
0x100360bd  push    ebx; struct Instance *
0x100360be  mov     ecx, edi; this
0x100360c0  call    ?Delete@Table@@QAEXPAVInstance@@AAVErr@@@Z; Table::Delete(Instance *,Err &)
0x100360c5  push    ebx; struct Instance *
0x100360c6  mov     ecx, edi; this
0x100360c8  call    ?Release@Table@@QAEJPAVInstance@@@Z; Table::Release(Instance *)
0x100360cd  test    [ebp+var_28], 0FFFFFFFEh
0x100360d4  jz      short loc_1003613B
0x100360d6  mov     eax, [ebp+Block]
0x100360d9  test    eax, eax
0x100360db  jz      short loc_100360E6
0x100360dd  push    eax; Block
0x100360de  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100360e3  add     esp, 4
0x100360e6  mov     eax, [ebp+var_18]
0x100360e9  test    eax, eax
0x100360eb  jz      short loc_1003613B
0x100360ed  push    eax; Block
0x100360ee  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100360f3  add     esp, 4
0x100360f6  jmp     short loc_1003613B
0x100360f8  test    byte ptr [esi], 8
0x100360fb  jz      short loc_1003613B
0x100360fd  mov     [ebp+var_28], 1
0x10036104  lea     eax, [ebp+var_28]
0x10036107  mov     [ebp+var_4], 3
0x1003610e  push    eax; struct Err *
0x1003610f  push    ebx; struct Instance *
0x10036110  mov     ecx, edi; this
0x10036112  call    ?Delete@Table@@QAEXPAVInstance@@AAVErr@@@Z; Table::Delete(Instance *,Err &)
0x10036117  mov     ebx, [ebp+var_10]
0x1003611a  push    1; void *
0x1003611c  mov     eax, [ebx]
0x1003611e  mov     esi, [eax]
0x10036120  mov     ecx, esi
0x10036122  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10036128  mov     ecx, ebx
0x1003612a  call    esi
0x1003612c  lea     ecx, [ebp+var_28]; this
0x1003612f  mov     [ebp+var_10], 0
0x10036136  call    ??1Err@@QAE@XZ; Err::~Err(void)
0x1003613b  mov     eax, [ebp+var_10]
0x1003613e  mov     ecx, [ebp+var_C]
0x10036141  mov     large fs:0, ecx
0x10036148  pop     ecx
0x10036149  pop     edi
0x1003614a  pop     esi
0x1003614b  pop     ebx
0x1003614c  mov     esp, ebp
0x1003614e  pop     ebp
0x1003614f  retn    10h
0x10060b60  push    778h; unsigned int
0x10060b65  mov     eax, [ebp+var_14]
0x10060b68  push    eax; Block
0x10060b69  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x10060b6e  add     esp, 8
0x10060b71  retn
0x10060b72  push    16Ch; unsigned int
0x10060b77  mov     eax, [ebp+var_14]
0x10060b7a  push    eax; Block
0x10060b7b  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x10060b80  add     esp, 8
0x10060b83  retn
0x10060b84  lea     ecx, [ebp+var_28]; this
0x10060b87  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x10060b8c  lea     ecx, [ebp+var_28]; this
0x10060b8f  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x10060b99  nop
0x10060b9a  nop
0x10060b9b  mov     edx, [esp-4+arg_4]
0x10060b9f  lea     eax, [edx+0Ch]
0x10060ba2  mov     ecx, [edx-2Ch]
0x10060ba5  xor     ecx, eax; StackCookie
0x10060ba7  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10060bac  mov     eax, offset stru_10063864
0x10060bb1  jmp     ___CxxFrameHandler3
```
