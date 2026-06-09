# Spacemap::Create(Transaction *,Err &,ulong)

- ea: `0x10047eb0`
- end: `0x100480f1`
- name: `?Create@Spacemap@@QAEKPAVTransaction@@AAVErr@@K@Z`
- size: `577`
- prototype: `unsigned int __thiscall(Spacemap *__hidden this, struct Transaction *, struct Err *, unsigned int)`
- caller_count: `7`
- callee_count: `13`
- tags: `file_ops, installer_update`

## callers

- `0x10021720`
- `0x10031300`
- `0x10045640`
- `0x10046080`
- `0x10050bc0`
- `0x10052e30`
- `0x100544e0`

## callees

- `0x1000eb60`
- `0x1000f750`
- `0x1000fc30`
- `0x10010580`
- `0x10023730`
- `0x100237e0`
- `0x10024f60`
- `0x10047eb0`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e798`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
int __thiscall Spacemap::Create(Spacemap *this, struct Transaction *a2, struct Err *a3, unsigned int a4)
{
  _DWORD *v5; // esi
  unsigned int v6; // eax
  int v7; // ecx
  void *v8; // eax
  struct Err *v9; // esi
  int v10; // esi
  _DWORD *v11; // eax
  unsigned int v12; // eax
  int v13; // ecx
  int v15[3]; // [esp+14h] [ebp-C8h] BYREF
  void *Block; // [esp+20h] [ebp-BCh]
  void *v17; // [esp+24h] [ebp-B8h]
  int v18; // [esp+28h] [ebp-B4h] BYREF
  int v19; // [esp+2Ch] [ebp-B0h]
  int v20; // [esp+34h] [ebp-A8h]
  void *v21; // [esp+38h] [ebp-A4h]
  struct Err *v22; // [esp+3Ch] [ebp-A0h]
  unsigned __int8 Src; // [esp+40h] [ebp-9Ch] BYREF
  int v24; // [esp+41h] [ebp-9Bh]
  char v25; // [esp+45h] [ebp-97h] BYREF
  int v26; // [esp+D8h] [ebp-4h]

  v22 = a3;
  v18 = 0;
  v19 = 0;
  v26 = 1;
  v15[0] = 1;
  Src = 0;
  *(_DWORD *)this = *((_DWORD *)a2 + 2);
  *((_DWORD *)this + 1) = a2;
  v24 = 0;
  v5 = operator new(0xCu);
  v21 = v5;
  *v5 = &v25;
  v5[1] = 128;
  v5[2] = 0;
  Bitmap::Clear((Bitmap *)v5, 0, 0x400u, a3);
  operator delete(v5);
  if ( a4 )
  {
    Database::ReadPageForUpdate(
      *(Database **)this,
      (struct PageRef *)&v18,
      a4 >> 8,
      (void **)a3,
      *((struct Transaction **)this + 1),
      0);
    if ( (*(_BYTE *)a3 & 8) != 0 )
      goto LABEL_9;
    v6 = DataPage::Insert((DataPage *)&v18, &Src, 0x85u);
    *((_DWORD *)this + 2) = v6;
    if ( v6 )
    {
      v7 = v18;
      *(_DWORD *)(v18 + 4 * *(_DWORD *)(v18 + 24) + 28) |= 8u;
      ++*(_DWORD *)(v7 + 64);
    }
  }
  if ( *((_DWORD *)this + 2) )
    goto LABEL_11;
  v8 = (void *)(*(int (__thiscall **)(_DWORD, _DWORD, struct Err *))(**(_DWORD **)this + 4))(*(_DWORD *)this, 0, v22);
  v9 = v22;
  v21 = v8;
  if ( (*(_BYTE *)v22 & 8) != 0 )
  {
LABEL_9:
    *((_DWORD *)this + 2) = 0;
    v10 = 0;
    goto LABEL_12;
  }
  Database::DontReadPage(
    *(Database **)this,
    (struct PageRef *)&v18,
    (unsigned int)v8,
    v22,
    *((struct Transaction **)this + 1));
  if ( (*(_BYTE *)v9 & 8) != 0 )
  {
    (*(void (__thiscall **)(_DWORD, void *, int, int *))(**(_DWORD **)this + 8))(*(_DWORD *)this, v21, 1, v15);
    goto LABEL_9;
  }
  v11 = (_DWORD *)v19;
  v20 = 0;
  *(_WORD *)(v19 + 8) = 0;
  *v11 = 133562625;
  v11[1] = 0;
  v12 = DataPage::Insert((DataPage *)&v18, &Src, 0x85u);
  v13 = v18;
  *((_DWORD *)this + 2) = v12;
  *(_DWORD *)(v13 + 4 * *(_DWORD *)(v13 + 24) + 28) |= 8u;
  ++*(_DWORD *)(v13 + 64);
LABEL_11:
  v10 = *((_DWORD *)this + 2);
LABEL_12:
  if ( (v15[0] & 0xFFFFFFFE) != 0 )
  {
    if ( Block )
      operator delete[](Block);
    if ( v17 )
      operator delete[](v17);
  }
  if ( v18 )
    --*(_WORD *)(v18 + 76);
  return v10;
}

```

## disassembly

```asm
0x10047eb0  mov     edi, edi
0x10047eb2  push    ebp
0x10047eb3  mov     ebp, esp
0x10047eb5  push    0FFFFFFFFh
0x10047eb7  push    offset ?Create@Spacemap@@QAEKPAVTransaction@@AAVErr@@K@Z_SEH
0x10047ebc  mov     eax, large fs:0
0x10047ec2  push    eax
0x10047ec3  sub     esp, 0C0h
0x10047ec9  mov     eax, ___security_cookie
0x10047ece  xor     eax, ebp
0x10047ed0  mov     [ebp+var_14], eax
0x10047ed3  push    ebx
0x10047ed4  push    esi
0x10047ed5  push    edi
0x10047ed6  push    eax
0x10047ed7  lea     eax, [ebp+var_C]
0x10047eda  mov     large fs:0, eax
0x10047ee0  mov     ebx, ecx
0x10047ee2  mov     edi, [ebp+arg_4]
0x10047ee5  mov     [ebp+var_A0], edi
0x10047eeb  mov     [ebp+var_B4], 0
0x10047ef5  mov     [ebp+var_B0], 0
0x10047eff  mov     [ebp+var_4], 0
0x10047f06  mov     [ebp+var_C8], 1
0x10047f10  mov     ecx, [ebp+arg_0]
0x10047f13  mov     byte ptr [ebp+var_4], 1
0x10047f17  push    0Ch; Size
0x10047f19  mov     [ebp+Src], 0
0x10047f20  mov     eax, [ecx+8]
0x10047f23  mov     [ebx], eax
0x10047f25  mov     [ebx+4], ecx
0x10047f28  mov     [ebp+var_9B], 0
0x10047f32  call    ??2@YAPAXI@Z; operator new(uint)
0x10047f37  mov     esi, eax
0x10047f39  add     esp, 4
0x10047f3c  lea     eax, [ebp+var_97]
0x10047f42  mov     [ebp+var_A4], esi
0x10047f48  xor     edx, edx; unsigned int
0x10047f4a  mov     ecx, esi; this
0x10047f4c  push    edi; struct Err *
0x10047f4d  push    400h; unsigned int
0x10047f52  mov     [esi], eax
0x10047f54  mov     dword ptr [esi+4], 80h
0x10047f5b  mov     dword ptr [esi+8], 0
0x10047f62  call    ?Clear@Bitmap@@QAIXKKAAVErr@@@Z; Bitmap::Clear(ulong,ulong,Err &)
0x10047f67  push    0Ch; unsigned int
0x10047f69  push    esi; Block
0x10047f6a  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x10047f6f  mov     eax, [ebp+arg_8]
0x10047f72  add     esp, 8
0x10047f75  test    eax, eax
0x10047f77  jz      short loc_10047FC9
0x10047f79  mov     ecx, [ebx]; this
0x10047f7b  push    0; char
0x10047f7d  push    dword ptr [ebx+4]; struct Transaction *
0x10047f80  shr     eax, 8
0x10047f83  push    edi; struct Err *
0x10047f84  push    eax; unsigned int
0x10047f85  lea     eax, [ebp+var_B4]
0x10047f8b  push    eax; struct PageRef *
0x10047f8c  call    ?ReadPageForUpdate@Database@@QAEXAAVPageRef@@KAAVErr@@PAVTransaction@@I@Z; Database::ReadPageForUpdate(PageRef &,ulong,Err &,Transaction *,uint)
0x10047f91  test    byte ptr [edi], 8
0x10047f94  jnz     loc_10048039
0x10047f9a  push    85h; unsigned int
0x10047f9f  lea     eax, [ebp+Src]
0x10047fa5  push    eax; Src
0x10047fa6  lea     ecx, [ebp+var_B4]; this
0x10047fac  call    ?Insert@DataPage@@QAEKPBEI@Z; DataPage::Insert(uchar const *,uint)
0x10047fb1  mov     [ebx+8], eax
0x10047fb4  test    eax, eax
0x10047fb6  jz      short loc_10047FC9
0x10047fb8  mov     ecx, [ebp+var_B4]
0x10047fbe  mov     eax, [ecx+18h]
0x10047fc1  or      dword ptr [ecx+eax*4+1Ch], 8
0x10047fc6  inc     dword ptr [ecx+40h]
0x10047fc9  cmp     dword ptr [ebx+8], 0
0x10047fcd  jnz     loc_1004808E
0x10047fd3  mov     edi, [ebx]
0x10047fd5  push    [ebp+var_A0]; unsigned int
0x10047fdb  push    0; void *
0x10047fdd  mov     eax, [edi]
0x10047fdf  mov     esi, [eax+4]
0x10047fe2  mov     ecx, esi
0x10047fe4  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10047fea  mov     ecx, edi
0x10047fec  call    esi
0x10047fee  mov     esi, [ebp+var_A0]
0x10047ff4  mov     [ebp+var_A4], eax
0x10047ffa  test    byte ptr [esi], 8
0x10047ffd  jnz     short loc_10048039
0x10047fff  push    dword ptr [ebx+4]; struct Transaction *
0x10048002  mov     ecx, [ebx]; this
0x10048004  push    esi; struct Err *
0x10048005  push    eax; unsigned int
0x10048006  lea     eax, [ebp+var_B4]
0x1004800c  push    eax; struct PageRef *
0x1004800d  call    ?DontReadPage@Database@@QAEXAAVPageRef@@KAAVErr@@PAVTransaction@@@Z; Database::DontReadPage(PageRef &,ulong,Err &,Transaction *)
0x10048012  test    byte ptr [esi], 8
0x10048015  jz      short loc_10048044
0x10048017  mov     edi, [ebx]
0x10048019  lea     ecx, [ebp+var_C8]
0x1004801f  push    ecx
0x10048020  push    1; unsigned int
0x10048022  push    [ebp+var_A4]; void *
0x10048028  mov     eax, [edi]
0x1004802a  mov     esi, [eax+8]
0x1004802d  mov     ecx, esi
0x1004802f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10048035  mov     ecx, edi
0x10048037  call    esi
0x10048039  mov     dword ptr [ebx+8], 0
0x10048040  xor     esi, esi
0x10048042  jmp     short loc_10048091
0x10048044  mov     eax, [ebp+var_B0]
0x1004804a  xor     ecx, ecx
0x1004804c  push    85h; unsigned int
0x10048051  mov     [ebp+var_A8], ecx
0x10048057  mov     [eax+8], cx
0x1004805b  lea     ecx, [ebp+var_B4]; this
0x10048061  mov     dword ptr [eax], 7F60101h
0x10048067  mov     dword ptr [eax+4], 0
0x1004806e  lea     eax, [ebp+Src]
0x10048074  push    eax; Src
0x10048075  call    ?Insert@DataPage@@QAEKPBEI@Z; DataPage::Insert(uchar const *,uint)
0x1004807a  mov     ecx, [ebp+var_B4]
0x10048080  mov     [ebx+8], eax
0x10048083  mov     eax, [ecx+18h]
0x10048086  or      dword ptr [ecx+eax*4+1Ch], 8
0x1004808b  inc     dword ptr [ecx+40h]
0x1004808e  mov     esi, [ebx+8]
0x10048091  test    [ebp+var_C8], 0FFFFFFFEh
0x1004809b  jz      short loc_100480C3
0x1004809d  mov     eax, [ebp+Block]
0x100480a3  test    eax, eax
0x100480a5  jz      short loc_100480B0
0x100480a7  push    eax; Block
0x100480a8  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100480ad  add     esp, 4
0x100480b0  mov     eax, [ebp+var_B8]
0x100480b6  test    eax, eax
0x100480b8  jz      short loc_100480C3
0x100480ba  push    eax; Block
0x100480bb  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100480c0  add     esp, 4
0x100480c3  mov     eax, [ebp+var_B4]
0x100480c9  test    eax, eax
0x100480cb  jz      short loc_100480D1
0x100480cd  dec     word ptr [eax+4Ch]
0x100480d1  mov     eax, esi
0x100480d3  mov     ecx, [ebp+var_C]
0x100480d6  mov     large fs:0, ecx
0x100480dd  pop     ecx
0x100480de  pop     edi
0x100480df  pop     esi
0x100480e0  pop     ebx
0x100480e1  mov     ecx, [ebp+var_14]
0x100480e4  xor     ecx, ebp; StackCookie
0x100480e6  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100480eb  mov     esp, ebp
0x100480ed  pop     ebp
0x100480ee  retn    0Ch
0x10061540  lea     ecx, [ebp+var_B4]; this
0x10061546  jmp     ??1DataPage@@QAE@XZ; DataPage::~DataPage(void)
0x1006154b  lea     ecx, [ebp+var_C8]; this
0x10061551  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x1006155b  nop
0x1006155c  nop
0x1006155d  mov     edx, [esp-4+arg_4]
0x10061561  lea     eax, [edx+0Ch]
0x10061564  mov     ecx, [edx-0D0h]
0x1006156a  xor     ecx, eax; StackCookie
0x1006156c  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10061571  mov     ecx, [edx-8]
0x10061574  xor     ecx, eax; StackCookie
0x10061576  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1006157b  mov     eax, offset stru_10063F54
0x10061580  jmp     ___CxxFrameHandler3
```
