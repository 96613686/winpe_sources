# CONTEXT_CONTAINER::SetNamedContext(IHttpStoredContext *,ushort const *)

- ea: `0x180031830`
- end: `0x180031988`
- name: `?SetNamedContext@CONTEXT_CONTAINER@@UEAAJPEAVIHttpStoredContext@@PEBG@Z`
- size: `344`
- prototype: `int(CONTEXT_CONTAINER *__hidden this, struct IHttpStoredContext *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x18001ab30`
- `0x180031694`
- `0x180031830`
- `0x180037722`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180031881`
- `msvcrt!_wcsicmp` at `0x180031881`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800318b8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800318b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800318ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800318ec`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180031914`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180031914`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180031852`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180031852`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18003186f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18003186f`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18003195f`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18003195f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003192a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003192a`

## pseudocode

```c
__int64 __fastcall CONTEXT_CONTAINER::SetNamedContext(
        CONTEXT_CONTAINER *this,
        struct IHttpStoredContext *a2,
        const unsigned __int16 *a3)
{
  STRU *v3; // rdi
  __int64 i; // rsi
  unsigned int v8; // eax
  const wchar_t *Str; // rax
  __int64 v10; // rdx
  int v11; // esi
  int v12; // ecx
  int v13; // ebp
  HLOCAL v14; // rax
  HLOCAL v15; // rsi
  const void **v16; // rdx
  STRU *v17; // rax

  v3 = 0;
  if ( *((_BYTE *)this + 36) )
    CReaderWriterLock3::WriteLock((CONTEXT_CONTAINER *)((char *)this + 8));
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v8 = *((_DWORD *)this + 7);
    if ( (unsigned int)i >= v8 )
      break;
    Str = STRU::QueryStr(*(STRU **)(*((_QWORD *)this + 7) + 8 * i));
    if ( !_wcsicmp(Str, a3) )
    {
      v11 = -2147024811;
      goto LABEL_18;
    }
  }
  v12 = 8 * v8;
  if ( 8 * v8 + 8 > *((_DWORD *)this + 8) )
  {
    v13 = v12 + 40;
    v14 = LocalAlloc(0x40u, (unsigned int)(v12 + 40));
    v15 = v14;
    if ( !v14 )
    {
LABEL_17:
      v11 = -2147024882;
      goto LABEL_18;
    }
    v16 = (const void **)*((_QWORD *)this + 7);
    if ( v16 )
    {
      memcpy_0(v14, *v16, *((unsigned int *)this + 8));
      LocalFree(*((HLOCAL *)this + 7));
    }
    *((_QWORD *)this + 7) = v15;
    *((_DWORD *)this + 8) = v13;
  }
  v17 = (STRU *)operator new(0x40u);
  v3 = v17;
  if ( !v17 )
  {
    v3 = 0;
    goto LABEL_17;
  }
  STRU::STRU(v17);
  *((_QWORD *)v3 + 7) = a2;
  v11 = STRU::Copy(v3, a3);
  if ( v11 >= 0 )
  {
    v10 = *((unsigned int *)this + 7);
    *(_QWORD *)(*((_QWORD *)this + 7) + 8 * v10) = v3;
    v3 = 0;
    ++*((_DWORD *)this + 7);
  }
LABEL_18:
  if ( *((_BYTE *)this + 36) )
    CReaderWriterLock3::WriteUnlock((CONTEXT_CONTAINER *)((char *)this + 8));
  if ( v3 )
    NAMED_CONTEXT_RECORD::`scalar deleting destructor'(v3, v10);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180031830  push    rbx
0x180031832  push    rbp
0x180031833  push    rsi
0x180031834  push    rdi
0x180031835  push    r14
0x180031837  push    r15
0x180031839  sub     rsp, 28h
0x18003183d  xor     edi, edi
0x18003183f  mov     r14, r8
0x180031842  mov     r15, rdx
0x180031845  mov     rbx, rcx
0x180031848  cmp     [rcx+24h], dil
0x18003184c  jz      short loc_18003185E
0x18003184e  add     rcx, 8
0x180031852  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180031859  nop     dword ptr [rax+rax+00h]
0x18003185e  xor     esi, esi
0x180031860  mov     eax, [rbx+1Ch]
0x180031863  cmp     esi, eax
0x180031865  jnb     short loc_18003189F
0x180031867  mov     rcx, [rbx+38h]
0x18003186b  mov     rcx, [rcx+rsi*8]
0x18003186f  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180031876  nop     dword ptr [rax+rax+00h]
0x18003187b  mov     rcx, rax; String1
0x18003187e  mov     rdx, r14; String2
0x180031881  call    cs:__imp__wcsicmp
0x180031888  nop     dword ptr [rax+rax+00h]
0x18003188d  test    eax, eax
0x18003188f  jz      short loc_180031895
0x180031891  inc     esi
0x180031893  jmp     short loc_180031860
0x180031895  mov     esi, 80070055h
0x18003189a  jmp     loc_180031955
0x18003189f  lea     ecx, ds:0[rax*8]
0x1800318a6  lea     eax, [rcx+8]
0x1800318a9  cmp     eax, [rbx+20h]
0x1800318ac  jbe     short loc_1800318FF
0x1800318ae  lea     ebp, [rcx+28h]
0x1800318b1  mov     ecx, 40h ; '@'; uFlags
0x1800318b6  mov     edx, ebp; uBytes
0x1800318b8  call    cs:__imp_LocalAlloc
0x1800318bf  nop     dword ptr [rax+rax+00h]
0x1800318c4  mov     rsi, rax
0x1800318c7  test    rax, rax
0x1800318ca  jz      loc_180031950
0x1800318d0  mov     rdx, [rbx+38h]
0x1800318d4  test    rdx, rdx
0x1800318d7  jz      short loc_1800318F8
0x1800318d9  mov     r8d, [rbx+20h]; Size
0x1800318dd  mov     rcx, rax; void *
0x1800318e0  mov     rdx, [rdx]; Src
0x1800318e3  call    memcpy_0
0x1800318e8  mov     rcx, [rbx+38h]; hMem
0x1800318ec  call    cs:__imp_LocalFree
0x1800318f3  nop     dword ptr [rax+rax+00h]
0x1800318f8  mov     [rbx+38h], rsi
0x1800318fc  mov     [rbx+20h], ebp
0x1800318ff  mov     ecx, 40h ; '@'; Size
0x180031904  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031909  mov     rdi, rax
0x18003190c  test    rax, rax
0x18003190f  jz      short loc_18003194E
0x180031911  mov     rcx, rax
0x180031914  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18003191b  nop     dword ptr [rax+rax+00h]
0x180031920  mov     rdx, r14
0x180031923  mov     [rdi+38h], r15
0x180031927  mov     rcx, rdi
0x18003192a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180031931  nop     dword ptr [rax+rax+00h]
0x180031936  mov     esi, eax
0x180031938  test    eax, eax
0x18003193a  js      short loc_180031955
0x18003193c  mov     edx, [rbx+1Ch]
0x18003193f  mov     rcx, [rbx+38h]
0x180031943  mov     [rcx+rdx*8], rdi
0x180031947  xor     edi, edi
0x180031949  inc     dword ptr [rbx+1Ch]
0x18003194c  jmp     short loc_180031955
0x18003194e  xor     edi, edi
0x180031950  mov     esi, 8007000Eh
0x180031955  cmp     byte ptr [rbx+24h], 0
0x180031959  jz      short loc_18003196B
0x18003195b  lea     rcx, [rbx+8]
0x18003195f  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180031966  nop     dword ptr [rax+rax+00h]
0x18003196b  test    rdi, rdi
0x18003196e  jz      short loc_180031978
0x180031970  mov     rcx, rdi; this
0x180031973  call    ??_GNAMED_CONTEXT_RECORD@@QEAAPEAXI@Z; NAMED_CONTEXT_RECORD::`scalar deleting destructor'(uint)
0x180031978  mov     eax, esi
0x18003197a  add     rsp, 28h
0x18003197e  pop     r15
0x180031980  pop     r14
0x180031982  pop     rdi
0x180031983  pop     rsi
0x180031984  pop     rbp
0x180031985  pop     rbx
0x180031986  retn
```
