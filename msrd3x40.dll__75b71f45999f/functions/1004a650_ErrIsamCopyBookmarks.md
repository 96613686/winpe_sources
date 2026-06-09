# ErrIsamCopyBookmarks

- ea: `0x1004a650`
- end: `0x1004a993`
- name: `ErrIsamCopyBookmarks`
- size: `835`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x1004a9a0`

## callees

- `0x1000eb60`
- `0x1000f750`
- `0x1001ccc0`
- `0x10025e60`
- `0x10026140`
- `0x1004a650`
- `0x10052cc0`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
int __fastcall ErrIsamCopyBookmarks(int a1, int a2, Cursor *a3, unsigned __int8 a4, int a5, int *a6, unsigned int *a7)
{
  int v7; // ebx
  void *v8; // ecx
  int v9; // edi
  bool v10; // zf
  int v11; // eax
  int v12; // esi
  char v13; // al
  Cursor *v14; // edi
  Table *v15; // edi
  struct Instance *v16; // eax
  int v17; // esi
  int v19; // [esp+1Ch] [ebp-370h] BYREF
  int v20; // [esp+20h] [ebp-36Ch]
  void *Block; // [esp+28h] [ebp-364h]
  void *v22; // [esp+2Ch] [ebp-360h]
  void *v23; // [esp+30h] [ebp-35Ch]
  int v24; // [esp+34h] [ebp-358h]
  unsigned int v25; // [esp+38h] [ebp-354h] BYREF
  unsigned int v26[3]; // [esp+3Ch] [ebp-350h] BYREF
  void *v27; // [esp+48h] [ebp-344h]
  void *v28; // [esp+4Ch] [ebp-340h]
  int v29; // [esp+50h] [ebp-33Ch]
  Cursor *v30; // [esp+54h] [ebp-338h]
  unsigned int v31[200]; // [esp+58h] [ebp-334h] BYREF
  int v32; // [esp+388h] [ebp-4h]

  v24 = a2;
  v30 = a3;
  v26[0] = 1;
  v32 = 0;
  v7 = 0;
  v8 = *(void **)(a1 + 212);
  v25 = 0;
  v23 = v8;
  v19 = 1;
  v9 = a5;
  LOBYTE(v32) = 1;
  if ( a5 >= 0 )
  {
    v29 = 1;
  }
  else
  {
    v29 = -1;
    if ( a5 == 0x80000000 )
    {
      v9 = 0x7FFFFFFF;
      a5 = 0x7FFFFFFF;
    }
    else
    {
      v9 = -a5;
      a5 = -a5;
    }
  }
  (*(void (__thiscall **)(Cursor *, _DWORD, unsigned int *))(*(_DWORD *)a3 + 20))(v30, 0, v26);
  if ( (v26[0] & 8) != 0 )
  {
    v10 = (v26[0] & 1) == 0;
  }
  else
  {
    do
    {
      if ( v7 >= v9 )
        break;
      v11 = a5 - v7;
      if ( (unsigned int)(a5 - v7) > 0xC8 )
        v11 = 200;
      v12 = (*(int (__thiscall **)(_DWORD, unsigned int *, int, int *))(**(_DWORD **)(v24 + 36) + 4))(
              *(_DWORD *)(v24 + 36),
              v31,
              v29 * v11,
              &v19);
      v13 = v19;
      if ( (v19 & 8) == 0 || (v19 & 1) == 0 && v20 == -1603 )
      {
        Cursor::InsertBookmarks(v30, v31, v12, (void *)a4, &v25, (struct Err *)v26);
        if ( (v26[0] & 8) != 0 )
          break;
        v13 = v19;
        v7 += v12;
      }
      v9 = a5;
    }
    while ( (v13 & 8) == 0 );
    v14 = v30;
    (*(void (__thiscall **)(Cursor *, int, unsigned int *))(*(_DWORD *)v30 + 20))(v30, 3, v26);
    if ( (v26[0] & 8) == 0 && ((v19 & 8) == 0 || (v19 & 1) == 0 && v20 == -1603) )
    {
      v15 = (Table *)(*(int (__thiscall **)(Cursor *))(*(_DWORD *)v14 + 60))(v14);
      v16 = (struct Instance *)(*(int (__thiscall **)(Cursor *))(*(_DWORD *)v30 + 56))(v30);
      Table::AddRecords(v15, v16, v7);
      if ( a6 )
        *a6 = v7;
      if ( a7 )
        *a7 = v25;
    }
    if ( (v19 & 8) == 0 )
      (*(void (__thiscall **)(_DWORD, int, int, unsigned int *))(**(_DWORD **)(v24 + 36) + 8))(
        *(_DWORD *)(v24 + 36),
        1,
        3 - (v29 != 1),
        v26);
    if ( v19 > (int)v26[0] )
      Err::operator=(&v19);
    v10 = (v26[0] & 1) == 0;
  }
  if ( v10 )
    v17 = RealJetError(v23);
  else
    v17 = 0;
  if ( (v19 & 0xFFFFFFFE) != 0 )
  {
    if ( Block )
      operator delete[](Block);
    if ( v22 )
      operator delete[](v22);
  }
  if ( (v26[0] & 0xFFFFFFFE) != 0 )
  {
    if ( v27 )
      operator delete[](v27);
    if ( v28 )
      operator delete[](v28);
  }
  return v17;
}

```

## disassembly

```asm
0x1004a650  mov     edi, edi
0x1004a652  push    ebp
0x1004a653  mov     ebp, esp
0x1004a655  push    0FFFFFFFFh
0x1004a657  push    offset ErrIsamCopyBookmarks_SEH
0x1004a65c  mov     eax, large fs:0
0x1004a662  push    eax
0x1004a663  sub     esp, 370h
0x1004a669  mov     eax, ___security_cookie
0x1004a66e  xor     eax, ebp
0x1004a670  mov     [ebp+var_14], eax
0x1004a673  push    ebx
0x1004a674  push    esi
0x1004a675  push    edi; unsigned int
0x1004a676  push    eax; void *
0x1004a677  lea     eax, [ebp+var_C]
0x1004a67a  mov     large fs:0, eax
0x1004a680  mov     [ebp+var_358], edx
0x1004a686  mov     eax, [ebp+arg_0]
0x1004a689  mov     edx, [ebp+arg_C]
0x1004a68c  mov     esi, [ebp+arg_10]
0x1004a68f  mov     [ebp+var_338], eax
0x1004a695  mov     [ebp+var_378], edx
0x1004a69b  mov     [ebp+var_37C], esi
0x1004a6a1  mov     [ebp+var_350], 1
0x1004a6ab  mov     [ebp+var_4], 0
0x1004a6b2  xor     ebx, ebx
0x1004a6b4  mov     ecx, [ecx+0D4h]
0x1004a6ba  mov     [ebp+var_354], ebx
0x1004a6c0  mov     [ebp+var_35C], ecx
0x1004a6c6  mov     [ebp+var_370], 1
0x1004a6d0  mov     edi, [ebp+arg_8]
0x1004a6d3  mov     byte ptr [ebp+var_4], 1
0x1004a6d7  test    edi, edi
0x1004a6d9  jns     short loc_1004A6FE
0x1004a6db  mov     [ebp+var_33C], 0FFFFFFFFh
0x1004a6e5  cmp     edi, 80000000h
0x1004a6eb  jnz     short loc_1004A6F7
0x1004a6ed  mov     edi, 7FFFFFFFh
0x1004a6f2  mov     [ebp+arg_8], edi
0x1004a6f5  jmp     short loc_1004A708
0x1004a6f7  neg     edi
0x1004a6f9  mov     [ebp+arg_8], edi
0x1004a6fc  jmp     short loc_1004A708
0x1004a6fe  mov     [ebp+var_33C], 1
0x1004a708  movzx   ecx, byte ptr [ebp+arg_4]
0x1004a70c  mov     eax, [eax]
0x1004a70e  mov     [ebp+var_374], ecx
0x1004a714  lea     ecx, [ebp+var_350]
0x1004a71a  push    ecx; unsigned int
0x1004a71b  push    0; void *
0x1004a71d  mov     esi, [eax+14h]
0x1004a720  mov     ecx, esi
0x1004a722  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004a728  mov     ecx, [ebp+var_338]
0x1004a72e  call    esi
0x1004a730  mov     eax, [ebp+var_350]
0x1004a736  test    al, 8
0x1004a738  jz      short loc_1004A741
0x1004a73a  test    al, 1
0x1004a73c  jmp     loc_1004A8F6
0x1004a741  test    byte ptr [ebp+var_370], 8
0x1004a748  jnz     loc_1004A7FC
0x1004a74e  mov     ecx, 0C8h
0x1004a753  cmp     ebx, edi
0x1004a755  jge     loc_1004A7FC
0x1004a75b  mov     eax, [ebp+var_358]
0x1004a761  mov     edi, [eax+24h]
0x1004a764  mov     eax, [edi]
0x1004a766  mov     esi, [eax+4]
0x1004a769  mov     eax, [ebp+arg_8]
0x1004a76c  sub     eax, ebx
0x1004a76e  cmp     eax, 0C8h
0x1004a773  cmova   eax, ecx
0x1004a776  lea     ecx, [ebp+var_370]
0x1004a77c  imul    eax, [ebp+var_33C]
0x1004a783  push    ecx
0x1004a784  mov     ecx, esi
0x1004a786  push    eax; unsigned int
0x1004a787  lea     eax, [ebp+var_334]
0x1004a78d  push    eax; void *
0x1004a78e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004a794  mov     ecx, edi
0x1004a796  call    esi
0x1004a798  mov     esi, eax
0x1004a79a  mov     eax, [ebp+var_370]
0x1004a7a0  test    al, 8
0x1004a7a2  jz      short loc_1004A7B4
0x1004a7a4  test    al, 1
0x1004a7a6  jnz     short loc_1004A7EC
0x1004a7a8  cmp     [ebp+var_36C], 0FFFFF9BDh
0x1004a7b2  jnz     short loc_1004A7EC
0x1004a7b4  mov     ecx, [ebp+var_338]; this
0x1004a7ba  lea     eax, [ebp+var_350]
0x1004a7c0  push    eax; struct Err *
0x1004a7c1  lea     eax, [ebp+var_354]
0x1004a7c7  push    eax; unsigned int *
0x1004a7c8  push    [ebp+var_374]; void *
0x1004a7ce  lea     eax, [ebp+var_334]
0x1004a7d4  push    esi; int
0x1004a7d5  push    eax; unsigned int *
0x1004a7d6  call    ?InsertBookmarks@Cursor@@QAEHPAKHH0AAVErr@@@Z; Cursor::InsertBookmarks(ulong *,int,int,ulong *,Err &)
0x1004a7db  test    byte ptr [ebp+var_350], 8
0x1004a7e2  jnz     short loc_1004A7FC
0x1004a7e4  mov     eax, [ebp+var_370]
0x1004a7ea  add     ebx, esi
0x1004a7ec  mov     edi, [ebp+arg_8]
0x1004a7ef  mov     ecx, 0C8h
0x1004a7f4  test    al, 8
0x1004a7f6  jz      loc_1004A753
0x1004a7fc  mov     edi, [ebp+var_338]
0x1004a802  lea     ecx, [ebp+var_350]
0x1004a808  push    ecx; unsigned int
0x1004a809  push    3; void *
0x1004a80b  mov     eax, [edi]
0x1004a80d  mov     esi, [eax+14h]
0x1004a810  mov     ecx, esi
0x1004a812  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004a818  mov     ecx, edi
0x1004a81a  call    esi
0x1004a81c  test    byte ptr [ebp+var_350], 8
0x1004a823  jnz     short loc_1004A894
0x1004a825  mov     eax, [ebp+var_370]
0x1004a82b  test    al, 8
0x1004a82d  jz      short loc_1004A83F
0x1004a82f  test    al, 1
0x1004a831  jnz     short loc_1004A894
0x1004a833  cmp     [ebp+var_36C], 0FFFFF9BDh
0x1004a83d  jnz     short loc_1004A894
0x1004a83f  mov     eax, [edi]
0x1004a841  mov     esi, [eax+3Ch]
0x1004a844  mov     ecx, esi
0x1004a846  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004a84c  mov     ecx, edi
0x1004a84e  call    esi
0x1004a850  mov     edi, eax
0x1004a852  mov     eax, [ebp+var_338]
0x1004a858  mov     eax, [eax]
0x1004a85a  mov     esi, [eax+38h]
0x1004a85d  mov     ecx, esi
0x1004a85f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004a865  mov     ecx, [ebp+var_338]
0x1004a86b  call    esi
0x1004a86d  push    ebx; int
0x1004a86e  push    eax; struct Instance *
0x1004a86f  mov     ecx, edi; this
0x1004a871  call    ?AddRecords@Table@@QAEJPAVInstance@@J@Z; Table::AddRecords(Instance *,long)
0x1004a876  mov     eax, [ebp+var_378]
0x1004a87c  test    eax, eax
0x1004a87e  jz      short loc_1004A882
0x1004a880  mov     [eax], ebx
0x1004a882  mov     ecx, [ebp+var_37C]
0x1004a888  test    ecx, ecx
0x1004a88a  jz      short loc_1004A894
0x1004a88c  mov     eax, [ebp+var_354]
0x1004a892  mov     [ecx], eax
0x1004a894  test    byte ptr [ebp+var_370], 8
0x1004a89b  jnz     short loc_1004A8CF
0x1004a89d  mov     eax, [ebp+var_358]
0x1004a8a3  mov     edi, [eax+24h]
0x1004a8a6  lea     eax, [ebp+var_350]
0x1004a8ac  push    eax
0x1004a8ad  mov     eax, [ebp+var_33C]
0x1004a8b3  dec     eax
0x1004a8b4  mov     esi, [edi]
0x1004a8b6  neg     eax
0x1004a8b8  sbb     eax, eax
0x1004a8ba  add     eax, 3
0x1004a8bd  mov     esi, [esi+8]
0x1004a8c0  mov     ecx, esi
0x1004a8c2  push    eax; unsigned int
0x1004a8c3  push    1; void *
0x1004a8c5  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004a8cb  mov     ecx, edi
0x1004a8cd  call    esi
0x1004a8cf  mov     eax, [ebp+var_370]
0x1004a8d5  cmp     eax, [ebp+var_350]
0x1004a8db  jle     short loc_1004A8EF
0x1004a8dd  lea     eax, [ebp+var_370]
0x1004a8e3  push    eax
0x1004a8e4  lea     ecx, [ebp+var_350]
0x1004a8ea  call    ??4Err@@QAEAAV0@ABV0@@Z; Err::operator=(Err const &)
0x1004a8ef  test    byte ptr [ebp+var_350], 1
0x1004a8f6  jz      short loc_1004A8FC
0x1004a8f8  xor     esi, esi
0x1004a8fa  jmp     short loc_1004A90F
0x1004a8fc  mov     ecx, [ebp+var_35C]; void *
0x1004a902  lea     edx, [ebp+var_350]
0x1004a908  call    RealJetError
0x1004a90d  mov     esi, eax
0x1004a90f  test    [ebp+var_370], 0FFFFFFFEh
0x1004a919  jz      short loc_1004A941
0x1004a91b  mov     eax, [ebp+Block]
0x1004a921  test    eax, eax
0x1004a923  jz      short loc_1004A92E
0x1004a925  push    eax; Block
0x1004a926  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004a92b  add     esp, 4
0x1004a92e  mov     eax, [ebp+var_360]
0x1004a934  test    eax, eax
0x1004a936  jz      short loc_1004A941
0x1004a938  push    eax; Block
0x1004a939  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004a93e  add     esp, 4
0x1004a941  test    [ebp+var_350], 0FFFFFFFEh
0x1004a94b  jz      short loc_1004A973
0x1004a94d  mov     eax, [ebp+var_344]
0x1004a953  test    eax, eax
0x1004a955  jz      short loc_1004A960
0x1004a957  push    eax; Block
0x1004a958  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004a95d  add     esp, 4
0x1004a960  mov     eax, [ebp+var_340]
0x1004a966  test    eax, eax
0x1004a968  jz      short loc_1004A973
0x1004a96a  push    eax; Block
0x1004a96b  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004a970  add     esp, 4
0x1004a973  mov     eax, esi
0x1004a975  mov     ecx, [ebp+var_C]
0x1004a978  mov     large fs:0, ecx
0x1004a97f  pop     ecx
0x1004a980  pop     edi
0x1004a981  pop     esi
0x1004a982  pop     ebx
0x1004a983  mov     ecx, [ebp+var_14]
0x1004a986  xor     ecx, ebp; StackCookie
0x1004a988  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004a98d  mov     esp, ebp
0x1004a98f  pop     ebp
0x1004a990  retn    14h
0x100615d0  lea     ecx, [ebp+var_350]; this
0x100615d6  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x100615db  lea     ecx, [ebp+var_370]; this
0x100615e1  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x100615eb  nop
0x100615ec  nop
0x100615ed  mov     edx, [esp-4+arg_4]
0x100615f1  lea     eax, [edx+0Ch]
0x100615f4  mov     ecx, [edx-380h]
0x100615fa  xor     ecx, eax; StackCookie
0x100615fc  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10061601  mov     ecx, [edx-8]
0x10061604  xor     ecx, eax; StackCookie
0x10061606  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1006160b  mov     eax, offset stru_10063FBC
0x10061610  jmp     ___CxxFrameHandler3
```
