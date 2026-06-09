# CXMLRowset::GetData(ulong,unsigned __int64,ushort,bool,ulong *,unsigned __int64 *,void *)

- ea: `0x180029170`
- end: `0x1800293ef`
- name: `?GetData@CXMLRowset@@UEAAJK_KG_NPEAKPEA_KPEAX@Z`
- size: `639`
- prototype: `__int64 __fastcall(CXMLRowset *__hidden this, unsigned int, unsigned __int64, unsigned __int16, bool, unsigned int *, unsigned __int64 *, void *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callees

- `0x180001db8`
- `0x180001dd4`
- `0x180003c38`
- `0x180004224`
- `0x1800042f4`
- `0x180004384`
- `0x18001b008`
- `0x180029170`
- `0x1800295d0`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall CXMLRowset::GetData(
        CXMLRowset *this,
        unsigned int a2,
        __int64 a3,
        unsigned __int16 a4,
        unsigned int a5,
        unsigned int *a6,
        unsigned __int64 *a7,
        _QWORD *a8)
{
  unsigned __int16 v8; // r10
  int v9; // edi
  __int64 v12; // rdx
  int *v13; // rbx
  CMetaData *v14; // rsi
  unsigned __int16 v15; // dx
  unsigned __int16 Type; // bp
  unsigned __int16 v17; // dx
  unsigned __int8 Precision; // r15
  unsigned __int16 v19; // dx
  unsigned __int8 Scale; // al
  unsigned int v21; // edx
  unsigned __int8 v22; // r12
  int v23; // r11d
  unsigned __int16 *v24; // rdi
  unsigned __int8 *v25; // rax
  unsigned __int8 *v26; // rsi
  int v27; // edx
  __int64 v28; // rax
  unsigned __int16 *i; // rcx
  int v31; // [rsp+B8h] [rbp+10h] BYREF
  __int64 v32; // [rsp+C0h] [rbp+18h]

  v32 = a3;
  v8 = a2 - 1;
  v9 = 0;
  v12 = 8LL * a2;
  if ( (_BYTE)a5 || (v13 = *(int **)(v12 + *((_QWORD *)this + 35)), (v13[1] & 0x10000000) != 0) )
    v13 = *(int **)(v12 + *((_QWORD *)this + 36));
  v14 = (CXMLRowset *)((char *)this + 304);
  a5 = v13[1] & 0xFEFFFFFF;
  if ( (CMetaData::mdGetFlags((CXMLRowset *)((char *)this + 304), v8) & 0x2000) != 0 )
  {
    if ( a7 )
      *a7 = *v13;
    *a8 = *((_QWORD *)v13 + 1);
    goto LABEL_33;
  }
  Type = CMetaData::mdGetType(v14, v15);
  Precision = CMetaData::mdGetPrecision(v14, v17);
  Scale = CMetaData::mdGetScale(v14, v19);
  v31 = 0;
  v22 = Scale;
  if ( v23 )
    goto LABEL_33;
  a5 = 8;
  v24 = (unsigned __int16 *)*((_QWORD *)v13 + 1);
  if ( Type == 128 )
  {
    v25 = MMMAlloc(*v13, v21);
    v26 = v25;
    if ( !v25 )
    {
      v9 = -2147024882;
      goto LABEL_33;
    }
    v9 = DecodeBin(v24, v25, *v13, &v31);
    if ( v9 < 0 )
      goto LABEL_32;
    v27 = v31;
    v24 = (unsigned __int16 *)v26;
  }
  else
  {
    v26 = 0;
    if ( Type == 135 || Type == 7 || Type == 64 )
    {
      v28 = *v13;
      if ( (int)v28 >= 19 )
        v24[10] = 32;
      if ( Type == 64 && (int)v28 > 19 )
      {
        for ( i = &v24[v28 - 1]; i >= v24 && *i == 48; --i )
          ;
        i[1] = 0;
      }
    }
    Type = 130;
    v27 = 2 * *v13;
  }
  v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned __int64 *, unsigned __int16 *, _QWORD *, __int64, _DWORD, unsigned int *, unsigned __int8, unsigned __int8, _DWORD))(**((_QWORD **)this + 66) + 24LL))(
         *((_QWORD *)this + 66),
         Type,
         a4,
         v27,
         a7,
         v24,
         a8,
         v32,
         0,
         &a5,
         Precision,
         v22,
         0);
  if ( v9 < 0 && (bidGblFlags & 2) != 0 && off_180049DE0[0] )
    bidTraceW(off_180049210[0], 219136, off_180049DE0[0], (unsigned int)v9, 214);
  if ( v26 )
LABEL_32:
    operator delete(v26);
LABEL_33:
  if ( a6 )
    *a6 = a5;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180029170  mov     [rsp+arg_0], rbx
0x180029175  mov     [rsp+arg_10], r8
0x18002917a  push    rbp
0x18002917b  push    rsi
0x18002917c  push    rdi
0x18002917d  push    r12
0x18002917f  push    r13
0x180029181  push    r14
0x180029183  push    r15
0x180029185  sub     rsp, 70h
0x180029189  mov     eax, edx
0x18002918b  lea     r10d, [rdx-1]
0x18002918f  xor     edi, edi
0x180029191  movzx   r13d, r9w
0x180029195  mov     r14, rcx
0x180029198  lea     rdx, ds:0[rax*8]
0x1800291a0  cmp     byte ptr [rsp+0A8h+arg_20], dil
0x1800291a8  jnz     short loc_1800291BE
0x1800291aa  mov     rax, [rcx+118h]
0x1800291b1  mov     rbx, [rdx+rax]
0x1800291b5  test    dword ptr [rbx+4], 10000000h
0x1800291bc  jz      short loc_1800291C9
0x1800291be  mov     rax, [rcx+120h]
0x1800291c5  mov     rbx, [rdx+rax]
0x1800291c9  mov     r11d, [rbx+4]
0x1800291cd  lea     rsi, [rcx+130h]
0x1800291d4  btr     r11d, 18h
0x1800291d9  movzx   edx, r10w; unsigned __int16
0x1800291dd  mov     rcx, rsi; this
0x1800291e0  mov     [rsp+0A8h+arg_20], r11d
0x1800291e8  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x1800291ed  bt      eax, 0Dh
0x1800291f1  jnb     short loc_18002921A
0x1800291f3  mov     rcx, [rsp+0A8h+arg_30]
0x1800291fb  test    rcx, rcx
0x1800291fe  jz      short loc_180029206
0x180029200  movsxd  rax, dword ptr [rbx]
0x180029203  mov     [rcx], rax
0x180029206  mov     rax, [rsp+0A8h+arg_38]
0x18002920e  mov     rcx, [rbx+8]
0x180029212  mov     [rax], rcx
0x180029215  jmp     loc_1800293BE
0x18002921a  mov     rcx, rsi; this
0x18002921d  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x180029222  mov     rcx, rsi; this
0x180029225  movzx   ebp, ax
0x180029228  call    ?mdGetPrecision@CMetaData@@QEAAEG@Z; CMetaData::mdGetPrecision(ushort)
0x18002922d  mov     rcx, rsi; this
0x180029230  mov     r15b, al
0x180029233  call    ?mdGetScale@CMetaData@@QEAAEG@Z; CMetaData::mdGetScale(ushort)
0x180029238  mov     [rsp+0A8h+arg_8], edi
0x18002923f  mov     r12b, al
0x180029242  test    r11d, r11d
0x180029245  jnz     loc_1800293BE
0x18002924b  mov     eax, 80h
0x180029250  mov     [rsp+0A8h+arg_20], 8
0x18002925b  mov     rdi, [rbx+8]
0x18002925f  cmp     bp, ax
0x180029262  jnz     short loc_1800292A9
0x180029264  mov     ecx, [rbx]; unsigned int
0x180029266  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18002926b  mov     rsi, rax
0x18002926e  test    rax, rax
0x180029271  jnz     short loc_18002927D
0x180029273  mov     edi, 8007000Eh
0x180029278  jmp     loc_1800293BE
0x18002927d  mov     r8d, [rbx]; unsigned int
0x180029280  lea     r9, [rsp+0A8h+arg_8]; int *
0x180029288  mov     rdx, rsi; unsigned __int8 *
0x18002928b  mov     rcx, rdi; unsigned __int16 *
0x18002928e  call    ?DecodeBin@@YAJPEAGPEAEKPEAJ@Z; DecodeBin(ushort *,uchar *,ulong,long *)
0x180029293  mov     edi, eax
0x180029295  test    eax, eax
0x180029297  js      loc_1800293B6
0x18002929d  mov     edx, [rsp+0A8h+arg_8]
0x1800292a4  mov     rdi, rsi
0x1800292a7  jmp     short loc_180029303
0x1800292a9  xor     esi, esi
0x1800292ab  mov     eax, 87h
0x1800292b0  lea     edx, [rsi+40h]
0x1800292b3  cmp     bp, ax
0x1800292b6  jz      short loc_1800292C3
0x1800292b8  cmp     bp, 7
0x1800292bc  jz      short loc_1800292C3
0x1800292be  cmp     bp, dx
0x1800292c1  jnz     short loc_1800292FA
0x1800292c3  movsxd  rax, dword ptr [rbx]
0x1800292c6  cmp     eax, 13h
0x1800292c9  jl      short loc_1800292D1
0x1800292cb  mov     word ptr [rdi+14h], 20h ; ' '
0x1800292d1  cmp     dx, bp
0x1800292d4  jnz     short loc_1800292FA
0x1800292d6  cmp     eax, 13h
0x1800292d9  jle     short loc_1800292FA
0x1800292db  lea     rcx, [rax-1]
0x1800292df  lea     rcx, [rdi+rcx*2]
0x1800292e3  jmp     short loc_1800292EF
0x1800292e5  cmp     word ptr [rcx], 30h ; '0'
0x1800292e9  jnz     short loc_1800292F4
0x1800292eb  sub     rcx, 2
0x1800292ef  cmp     rcx, rdi
0x1800292f2  jnb     short loc_1800292E5
0x1800292f4  xor     eax, eax
0x1800292f6  mov     [rcx+2], ax
0x1800292fa  mov     edx, [rbx]
0x1800292fc  mov     ebp, 82h
0x180029301  add     edx, edx
0x180029303  mov     rcx, [r14+210h]
0x18002930a  mov     r8, [rsp+0A8h+arg_38]
0x180029312  mov     [rsp+0A8h+var_48], 0
0x18002931a  mov     [rsp+0A8h+var_50], r12b
0x18002931f  mov     rax, [rcx]
0x180029322  mov     [rsp+0A8h+var_58], r15b
0x180029327  movsxd  r9, edx
0x18002932a  lea     rdx, [rsp+0A8h+arg_20]
0x180029332  mov     [rsp+0A8h+var_60], rdx
0x180029337  mov     rdx, [rsp+0A8h+arg_10]
0x18002933f  mov     rax, [rax+18h]
0x180029343  mov     [rsp+0A8h+var_68], 0
0x18002934b  mov     [rsp+0A8h+var_70], rdx
0x180029350  movzx   edx, bp
0x180029353  mov     [rsp+0A8h+var_78], r8
0x180029358  mov     r8, [rsp+0A8h+arg_30]
0x180029360  mov     [rsp+0A8h+var_80], rdi
0x180029365  mov     [rsp+0A8h+var_88], r8
0x18002936a  movzx   r8d, r13w
0x18002936e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029373  mov     edi, eax
0x180029375  test    eax, eax
0x180029377  jns     short loc_1800293B1
0x180029379  test    byte ptr cs:_bidGblFlags, 2
0x180029380  jz      short loc_1800293B1
0x180029382  mov     rax, cs:off_180049DE0; "<CXMLRowset::GetData|ADO|ERR>  HRESULT:"...
0x180029389  test    rax, rax
0x18002938c  jz      short loc_1800293B1
0x18002938e  mov     r8, cs:off_180049DE0; "<CXMLRowset::GetData|ADO|ERR>  HRESULT:"...
0x180029395  mov     r9d, edi
0x180029398  mov     rcx, cs:off_180049210; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002939f  mov     edx, 35800h
0x1800293a4  mov     dword ptr [rsp+0A8h+var_88], 0D6h
0x1800293ac  call    _bidTraceW
0x1800293b1  test    rsi, rsi
0x1800293b4  jz      short loc_1800293BE
0x1800293b6  mov     rcx, rsi; void *
0x1800293b9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800293be  mov     rcx, [rsp+0A8h+arg_28]
0x1800293c6  test    rcx, rcx
0x1800293c9  jz      short loc_1800293D4
0x1800293cb  mov     eax, [rsp+0A8h+arg_20]
0x1800293d2  mov     [rcx], eax
0x1800293d4  mov     rbx, [rsp+0A8h+arg_0]
0x1800293dc  mov     eax, edi
0x1800293de  add     rsp, 70h
0x1800293e2  pop     r15
0x1800293e4  pop     r14
0x1800293e6  pop     r13
0x1800293e8  pop     r12
0x1800293ea  pop     rdi
0x1800293eb  pop     rsi
0x1800293ec  pop     rbp
0x1800293ed  retn
```
