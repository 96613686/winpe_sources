# CRecordGroup::Emulate(CRecordGroup *,bool)

- ea: `0x18009c178`
- end: `0x18009c36e`
- name: `?Emulate@CRecordGroup@@QEAAJPEAV1@_N@Z`
- size: `502`
- prototype: `__int64 __fastcall(CRecordGroup *__hidden this, struct CRecordGroup *, bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18004a31c`
- `0x1800af1f0`

## callees

- `0x1800279f0`
- `0x180027c4c`
- `0x180027c8c`
- `0x18002a0f0`
- `0x18002cd84`
- `0x1800570ec`
- `0x18009c178`
- `0x1800cdad2`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x18009c201`
- `MSDART!MpHeapAlloc` at `0x18009c226`
- `MSDART!MpHeapAlloc` at `0x18009c201`
- `MSDART!MpHeapAlloc` at `0x18009c226`
- `MSDART!MpHeapFree` at `0x18009c290`
- `MSDART!MpHeapFree` at `0x18009c290`
- `ole32!CoTaskMemAlloc` at `0x18009c304`
- `ole32!CoTaskMemAlloc` at `0x18009c304`

## pseudocode

```c
__int64 __fastcall CRecordGroup::Emulate(CRecordGroup *this, struct CRecordGroup *a2, char a3)
{
  __int64 result; // rax
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // r8
  void *v10; // rcx
  __int64 v11; // rax
  void *v12; // rcx
  SIZE_T v13; // rcx
  int v14; // edx
  void *v15; // rax
  int v16; // eax
  unsigned int v17; // ecx

  *(_QWORD *)this = *(_QWORD *)a2;
  result = CRecordGroup::AddRefRows(a2);
  if ( (int)result < 0 )
    return result;
  result = CRecordGroup::ReleaseRows(this);
  if ( (int)result < 0 && !a3 )
    return result;
  *((_BYTE *)this + 56) = *((_BYTE *)a2 + 56);
  *((_BYTE *)this + 57) = *((_BYTE *)a2 + 57);
  v7 = *((_QWORD *)a2 + 1);
  *((_QWORD *)this + 1) = v7;
  *((_BYTE *)this + 16) = *((_BYTE *)a2 + 16);
  if ( *((_BYTE *)a2 + 96) )
  {
    CRecordGroup::FreeRows(this);
    v8 = MpHeapAlloc(g_hHeapHandle, 10485760, 8LL * *((_QWORD *)this + 1) + 8);
    v9 = *((_QWORD *)this + 1);
    v10 = g_hHeapHandle;
    *((_QWORD *)this + 5) = v8;
    v11 = MpHeapAlloc(v10, 10485760, 8 * v9 + 8);
    v12 = (void *)*((_QWORD *)this + 5);
    *((_QWORD *)this + 6) = v11;
    if ( !v12 || !v11 )
      return 2147942414LL;
    memcpy_0(v12, *((const void **)a2 + 5), 8LL * *((_QWORD *)this + 1));
    memcpy_0(*((void **)this + 6), *((const void **)a2 + 6), 8LL * *((_QWORD *)this + 1));
    *((_BYTE *)this + 96) = 1;
  }
  else
  {
    if ( *((_BYTE *)this + 96) && *((_QWORD *)this + 6) )
    {
      MpHeapFree(g_hHeapHandle, *((_QWORD *)this + 6));
      v7 = *((_QWORD *)this + 1);
      *((_QWORD *)this + 6) = 0;
    }
    *((_BYTE *)this + 96) = 0;
    result = CRecordGroup::AllocateHRowRange(this, v7, (unsigned __int64 **)this + 5);
    if ( (int)result < 0 )
      return result;
    memcpy_0(*((void **)this + 5), *((const void **)a2 + 5), 8LL * *((_QWORD *)this + 1));
  }
  CRecordGroup::FreeBookmark(this);
  v13 = *((_QWORD *)a2 + 8);
  *((_QWORD *)this + 8) = v13;
  v14 = *((_DWORD *)a2 + 15);
  *((_DWORD *)this + 15) = v14;
  *((_QWORD *)this + 4) = *((_QWORD *)a2 + 4);
  *((_BYTE *)this + 97) = *((_BYTE *)a2 + 97);
  if ( v14 )
  {
    if ( *((_QWORD *)a2 + 9) )
    {
      v15 = CoTaskMemAlloc(v13);
      *((_QWORD *)this + 9) = v15;
      if ( !v15 )
        return 2147942414LL;
      memcpy_0(v15, *((const void **)a2 + 9), *((_QWORD *)this + 8));
    }
    else
    {
      *((_QWORD *)this + 9) = 0;
    }
  }
  else
  {
    *((_QWORD *)this + 9) = *((_QWORD *)a2 + 9);
  }
  v16 = CRecordGroup::SetStatus(this, *((_QWORD *)a2 + 11), *((unsigned int *const *)a2 + 10));
  v17 = 0;
  if ( v16 < 0 )
    return (unsigned int)v16;
  return v17;
}

```

## disassembly

```asm
0x18009c178  mov     [rsp+arg_0], rbx
0x18009c17d  mov     [rsp+arg_8], rsi
0x18009c182  push    rdi
0x18009c183  sub     rsp, 20h
0x18009c187  mov     rax, [rdx]
0x18009c18a  mov     rbx, rcx
0x18009c18d  mov     [rcx], rax
0x18009c190  mov     sil, r8b
0x18009c193  mov     rcx, rdx; this
0x18009c196  mov     rdi, rdx
0x18009c199  call    ?AddRefRows@CRecordGroup@@QEAAJXZ; CRecordGroup::AddRefRows(void)
0x18009c19e  test    eax, eax
0x18009c1a0  js      loc_18009C35D
0x18009c1a6  mov     rcx, rbx; this
0x18009c1a9  call    ?ReleaseRows@CRecordGroup@@QEAAJXZ; CRecordGroup::ReleaseRows(void)
0x18009c1ae  test    eax, eax
0x18009c1b0  jns     short loc_18009C1BB
0x18009c1b2  test    sil, sil
0x18009c1b5  jz      loc_18009C35D
0x18009c1bb  mov     al, [rdi+38h]
0x18009c1be  mov     [rbx+38h], al
0x18009c1c1  mov     al, [rdi+39h]
0x18009c1c4  mov     [rbx+39h], al
0x18009c1c7  mov     rdx, [rdi+8]
0x18009c1cb  mov     [rbx+8], rdx
0x18009c1cf  mov     al, [rdi+10h]
0x18009c1d2  mov     [rbx+10h], al
0x18009c1d5  cmp     byte ptr [rdi+60h], 0
0x18009c1d9  jz      loc_18009C278
0x18009c1df  mov     rcx, rbx; this
0x18009c1e2  call    ?FreeRows@CRecordGroup@@QEAAXXZ; CRecordGroup::FreeRows(void)
0x18009c1e7  mov     r8, [rbx+8]
0x18009c1eb  mov     esi, 0A00000h
0x18009c1f0  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18009c1f7  mov     edx, esi
0x18009c1f9  lea     r8, ds:8[r8*8]
0x18009c201  call    cs:__imp_MpHeapAlloc
0x18009c208  nop     dword ptr [rax+rax+00h]
0x18009c20d  mov     r8, [rbx+8]
0x18009c211  mov     edx, esi
0x18009c213  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18009c21a  mov     [rbx+28h], rax
0x18009c21e  lea     r8, ds:8[r8*8]
0x18009c226  call    cs:__imp_MpHeapAlloc
0x18009c22d  nop     dword ptr [rax+rax+00h]
0x18009c232  mov     rcx, [rbx+28h]; void *
0x18009c236  mov     [rbx+30h], rax
0x18009c23a  test    rcx, rcx
0x18009c23d  jz      loc_18009C319
0x18009c243  test    rax, rax
0x18009c246  jz      loc_18009C319
0x18009c24c  mov     r8, [rbx+8]
0x18009c250  mov     rdx, [rdi+28h]; Src
0x18009c254  shl     r8, 3; Size
0x18009c258  call    memcpy_0
0x18009c25d  mov     r8, [rbx+8]
0x18009c261  mov     rdx, [rdi+30h]; Src
0x18009c265  mov     rcx, [rbx+30h]; void *
0x18009c269  shl     r8, 3; Size
0x18009c26d  call    memcpy_0
0x18009c272  mov     byte ptr [rbx+60h], 1
0x18009c276  jmp     short loc_18009C2D5
0x18009c278  cmp     byte ptr [rbx+60h], 0
0x18009c27c  jz      short loc_18009C2A8
0x18009c27e  cmp     qword ptr [rbx+30h], 0
0x18009c283  jz      short loc_18009C2A8
0x18009c285  mov     rdx, [rbx+30h]
0x18009c289  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18009c290  call    cs:__imp_MpHeapFree
0x18009c297  nop     dword ptr [rax+rax+00h]
0x18009c29c  mov     rdx, [rbx+8]; __int64
0x18009c2a0  mov     qword ptr [rbx+30h], 0
0x18009c2a8  lea     r8, [rbx+28h]; unsigned __int64 **
0x18009c2ac  mov     byte ptr [rbx+60h], 0
0x18009c2b0  mov     rcx, rbx; this
0x18009c2b3  call    ?AllocateHRowRange@CRecordGroup@@QEAAJ_JPEAPEA_K@Z; CRecordGroup::AllocateHRowRange(__int64,unsigned __int64 * *)
0x18009c2b8  test    eax, eax
0x18009c2ba  js      loc_18009C35D
0x18009c2c0  mov     r8, [rbx+8]
0x18009c2c4  mov     rdx, [rdi+28h]; Src
0x18009c2c8  mov     rcx, [rbx+28h]; void *
0x18009c2cc  shl     r8, 3; Size
0x18009c2d0  call    memcpy_0
0x18009c2d5  mov     rcx, rbx; this
0x18009c2d8  call    ?FreeBookmark@CRecordGroup@@QEAAXXZ; CRecordGroup::FreeBookmark(void)
0x18009c2dd  mov     rcx, [rdi+40h]; cb
0x18009c2e1  mov     [rbx+40h], rcx
0x18009c2e5  mov     edx, [rdi+3Ch]
0x18009c2e8  mov     [rbx+3Ch], edx
0x18009c2eb  mov     rax, [rdi+20h]
0x18009c2ef  mov     [rbx+20h], rax
0x18009c2f3  mov     al, [rdi+61h]
0x18009c2f6  mov     [rbx+61h], al
0x18009c2f9  test    edx, edx
0x18009c2fb  jz      short loc_18009C33C
0x18009c2fd  cmp     qword ptr [rdi+48h], 0
0x18009c302  jz      short loc_18009C332
0x18009c304  call    cs:__imp_CoTaskMemAlloc
0x18009c30b  nop     dword ptr [rax+rax+00h]
0x18009c310  mov     [rbx+48h], rax
0x18009c314  test    rax, rax
0x18009c317  jnz     short loc_18009C320
0x18009c319  mov     eax, 8007000Eh
0x18009c31e  jmp     short loc_18009C35D
0x18009c320  mov     r8, [rbx+40h]; Size
0x18009c324  mov     rcx, rax; void *
0x18009c327  mov     rdx, [rdi+48h]; Src
0x18009c32b  call    memcpy_0
0x18009c330  jmp     short loc_18009C344
0x18009c332  mov     qword ptr [rbx+48h], 0
0x18009c33a  jmp     short loc_18009C344
0x18009c33c  mov     rax, [rdi+48h]
0x18009c340  mov     [rbx+48h], rax
0x18009c344  mov     r8, [rdi+50h]; unsigned int *
0x18009c348  mov     rcx, rbx; this
0x18009c34b  mov     rdx, [rdi+58h]; unsigned __int64
0x18009c34f  call    ?SetStatus@CRecordGroup@@QEAAJ_KQEAK@Z; CRecordGroup::SetStatus(unsigned __int64,ulong * const)
0x18009c354  xor     ecx, ecx
0x18009c356  test    eax, eax
0x18009c358  cmovs   ecx, eax
0x18009c35b  mov     eax, ecx
0x18009c35d  mov     rbx, [rsp+28h+arg_0]
0x18009c362  mov     rsi, [rsp+28h+arg_8]
0x18009c367  add     rsp, 20h
0x18009c36b  pop     rdi
0x18009c36c  retn
```
