# ArrayObj::DeleteRangeFromNameList(ulong,ulong)

- ea: `0x18006a7e8`
- end: `0x18006a90a`
- name: `?DeleteRangeFromNameList@ArrayObj@@IEAAXKK@Z`
- size: `290`
- prototype: `void(ArrayObj *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18004c154`

## callees

- `0x1800034cc`
- `0x1800132f8`
- `0x18002f3a4`
- `0x18003b5e0`
- `0x18006a7e8`
- `0x180077b08`
- `0x180077b88`
- `0x1800966e0`

## import_xrefs

- `msvcrt!_ltow` at `0x18006a8ac`
- `msvcrt!_ltow` at `0x18006a8ac`

## pseudocode

```c
void __fastcall ArrayObj::DeleteRangeFromNameList(ArrayObj *this, unsigned int a2, unsigned int a3)
{
  NameList *v3; // rsi
  int v6; // edx
  struct SYM *v7; // rax
  int v8; // r8d
  int i; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v10; // [rsp+34h] [rbp-CCh] BYREF
  struct VVAL *v11; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v12; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+50h] [rbp-B0h]
  __int128 v14; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v15; // [rsp+68h] [rbp-98h]
  wchar_t Buffer[256]; // [rsp+70h] [rbp-90h] BYREF

  v3 = (NameList *)*((_QWORD *)this + 2);
  v13 = 0;
  v12 = 0;
  v10 = 0;
  v11 = 0;
  if ( (unsigned int)ArrayObj::FSparseArray(this) )
  {
    v6 = -1;
    for ( i = -1; (unsigned int)CIndexedNameList::FGetNextId(v3, v6, &i, &v11, (struct SYM *)&v12); v6 = i )
    {
      if ( (unsigned int)FGetIndex((struct SYM *)&v12, &v10) && v10 >= a2 && v10 <= a3 )
        NameList::DeleteVvalById(v3, i, 0);
    }
  }
  else
  {
    while ( a2 <= a3 )
    {
      _ltow(a2, Buffer, 10);
      v15 = 0;
      v14 = 0;
      v7 = SYM::InitFromPsz((SYM *)&v14, Buffer);
      NameList::DeleteVval(v3, v7, v8);
      ++a2;
    }
  }
}

```

## disassembly

```asm
0x18006a7e8  mov     [rsp-8+arg_10], rbx
0x18006a7ed  push    rbp
0x18006a7ee  push    rsi
0x18006a7ef  push    rdi
0x18006a7f0  lea     rbp, [rsp-180h]
0x18006a7f8  sub     rsp, 280h
0x18006a7ff  mov     rax, cs:__security_cookie
0x18006a806  xor     rax, rsp
0x18006a809  mov     [rbp+190h+var_20], rax
0x18006a810  mov     rsi, [rcx+10h]
0x18006a814  xor     eax, eax
0x18006a816  xorps   xmm0, xmm0
0x18006a819  mov     [rsp+290h+var_240], rax
0x18006a81e  movups  [rsp+290h+var_250], xmm0
0x18006a823  mov     [rsp+290h+var_25C], eax
0x18006a827  mov     edi, r8d
0x18006a82a  mov     ebx, edx
0x18006a82c  mov     [rsp+290h+var_258], 0
0x18006a835  call    ?FSparseArray@ArrayObj@@QEAAHXZ; ArrayObj::FSparseArray(void)
0x18006a83a  test    eax, eax
0x18006a83c  jz      loc_18006A8E3
0x18006a842  or      edx, 0FFFFFFFFh
0x18006a845  mov     [rsp+290h+var_260], edx
0x18006a849  jmp     short loc_18006A87D
0x18006a84b  lea     rdx, [rsp+290h+var_25C]; unsigned int *
0x18006a850  lea     rcx, [rsp+290h+var_250]; struct SYM *
0x18006a855  call    ?FGetIndex@@YAHPEAUSYM@@PEAK@Z; FGetIndex(SYM *,ulong *)
0x18006a85a  test    eax, eax
0x18006a85c  jz      short loc_18006A879
0x18006a85e  cmp     [rsp+290h+var_25C], ebx
0x18006a862  jb      short loc_18006A879
0x18006a864  cmp     [rsp+290h+var_25C], edi
0x18006a868  ja      short loc_18006A879
0x18006a86a  mov     edx, [rsp+290h+var_260]; int
0x18006a86e  xor     r8d, r8d; int
0x18006a871  mov     rcx, rsi; this
0x18006a874  call    ?DeleteVvalById@NameList@@QEAAJJH@Z; NameList::DeleteVvalById(long,int)
0x18006a879  mov     edx, [rsp+290h+var_260]; int
0x18006a87d  lea     rax, [rsp+290h+var_250]
0x18006a882  mov     rcx, rsi; this
0x18006a885  lea     r9, [rsp+290h+var_258]; struct VVAL **
0x18006a88a  mov     [rsp+290h+var_270], rax; struct SYM *
0x18006a88f  lea     r8, [rsp+290h+var_260]; int *
0x18006a894  call    ?FGetNextId@CIndexedNameList@@UEAAHJPEAJPEAPEAUVVAL@@PEAUSYM@@@Z; CIndexedNameList::FGetNextId(long,long *,VVAL * *,SYM *)
0x18006a899  test    eax, eax
0x18006a89b  jnz     short loc_18006A84B
0x18006a89d  jmp     short loc_18006A8E7
0x18006a89f  mov     r8d, 0Ah; Radix
0x18006a8a5  lea     rdx, [rsp+290h+Buffer]; Buffer
0x18006a8aa  mov     ecx, ebx; Value
0x18006a8ac  call    cs:__imp__ltow
0x18006a8b3  nop     dword ptr [rax+rax+00h]
0x18006a8b8  xor     eax, eax
0x18006a8ba  lea     rdx, [rsp+290h+Buffer]; unsigned __int16 *
0x18006a8bf  xorps   xmm0, xmm0
0x18006a8c2  mov     [rsp+290h+var_228], rax
0x18006a8c7  lea     rcx, [rsp+290h+var_238]; this
0x18006a8cc  movups  [rsp+290h+var_238], xmm0
0x18006a8d1  call    ?InitFromPsz@SYM@@QEAAPEAU1@PEBG@Z; SYM::InitFromPsz(ushort const *)
0x18006a8d6  mov     rdx, rax; struct SYM *
0x18006a8d9  mov     rcx, rsi; this
0x18006a8dc  call    ?DeleteVval@NameList@@QEAAJPEAUSYM@@H@Z; NameList::DeleteVval(SYM *,int)
0x18006a8e1  inc     ebx
0x18006a8e3  cmp     ebx, edi
0x18006a8e5  jbe     short loc_18006A89F
0x18006a8e7  mov     rcx, [rbp+190h+var_20]
0x18006a8ee  xor     rcx, rsp; StackCookie
0x18006a8f1  call    __security_check_cookie
0x18006a8f6  mov     rbx, [rsp+290h+arg_10]
0x18006a8fe  add     rsp, 280h
0x18006a905  pop     rdi
0x18006a906  pop     rsi
0x18006a907  pop     rbp
0x18006a908  retn
```
