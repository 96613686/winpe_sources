# CSimpStorageOpen::OpenStream(ushort const *,void *,ulong,ulong,IStream * *)

- ea: `0x18004eed0`
- end: `0x18004f09c`
- name: `?OpenStream@CSimpStorageOpen@@UEAAJPEBGPEAXKKPEAPEAUIStream@@@Z`
- size: `460`
- prototype: `int(CSimpStorageOpen *__hidden this, const unsigned __int16 *, void *, unsigned int, unsigned int, struct IStream **)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000e940`
- `0x180016140`
- `0x180021fb0`
- `0x18003f714`
- `0x180042800`
- `0x18004eac8`
- `0x18004eed0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f031`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f031`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004f026`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004f026`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004efba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004efba`

## pseudocode

```c
__int64 __fastcall CSimpStorageOpen::OpenStream(
        CSimpStorageOpen *this,
        const unsigned __int16 *a2,
        void *a3,
        unsigned int a4,
        unsigned int a5,
        struct IStream **a6)
{
  __int64 v9; // rbx
  __int64 result; // rax
  CSimpStream *v11; // rax
  CSimpStream *v12; // rdi
  void *v13; // rcx
  int v14; // ebp
  LONG v15; // ebp
  signed int LastError; // eax
  unsigned int v17; // edx
  signed int v18; // ebx
  _BYTE v19[64]; // [rsp+30h] [rbp-88h] BYREF
  __int16 v20; // [rsp+70h] [rbp-48h]

  v9 = *(_QWORD *)(*((_QWORD *)this + 78) + 80LL);
  v20 = 0;
  result = CExpParameterValidate::OpenStream(a2, a3, a4, a5, a6);
  if ( (int)result >= 0 )
  {
    if ( *((_QWORD *)this + 79) )
    {
      return 2147680257LL;
    }
    else if ( ((a4 - 16) & 0xFFFFFFFD) != 0 )
    {
      return 2147680511LL;
    }
    else if ( *((_DWORD *)this + 162) == 16 && a4 == 18 )
    {
      return 2147680261LL;
    }
    else
    {
      CDfName::Set((CDfName *)v19, a2);
      while ( 1 )
      {
        if ( !v9 )
          return (unsigned int)-2147287038;
        if ( !(unsigned int)CDirectory::NameCompare((const struct CDfName *)v19, (const struct CDfName *)v9) )
          break;
        v9 = *(_QWORD *)(v9 + 80);
      }
      v11 = (CSimpStream *)HeapAlloc(g_hHeap, 0, 0x40u);
      v12 = v11;
      if ( !v11 )
        return 2147680264LL;
      CSimpStream::CSimpStream(v11);
      *((_QWORD *)v12 + 6) = 0;
      *((_QWORD *)v12 + 1) = &CSimpStreamOpen::`vftable'{for `IMarshal'};
      *(_QWORD *)v12 = &CSimpStreamOpen::`vftable'{for `IStream'};
      v13 = (void *)*((_QWORD *)this + 8);
      *((_QWORD *)this + 79) = v9;
      v14 = *(_DWORD *)(v9 + 68) + 1;
      *((_QWORD *)v12 + 6) = v9;
      v15 = v14 << 9;
      *((_DWORD *)v12 + 5) = v15;
      *((_QWORD *)v12 + 5) = v13;
      *((_QWORD *)v12 + 4) = this;
      *((_DWORD *)v12 + 4) = 1;
      *((_DWORD *)v12 + 14) = a4;
      if ( SetFilePointer(v13, v15, 0, 0) == -1 )
      {
        LastError = GetLastError();
        v18 = LastError;
        if ( LastError > 0 )
          v18 = (unsigned __int16)LastError | 0x80070000;
        if ( v18 < 0 )
        {
          CSimpStreamOpen::`scalar deleting destructor'(v12, v17);
          v12 = 0;
          *((_QWORD *)this + 79) = 0;
        }
      }
      else
      {
        *((_DWORD *)v12 + 6) = v15;
        v18 = 0;
      }
      *a6 = v12;
      return (unsigned int)v18;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004eed0  mov     [rsp+arg_10], rbx
0x18004eed5  push    rbp
0x18004eed6  push    rsi
0x18004eed7  push    rdi
0x18004eed8  push    r14
0x18004eeda  push    r15
0x18004eedc  sub     rsp, 90h
0x18004eee3  mov     rax, cs:__security_cookie
0x18004eeea  xor     rax, rsp
0x18004eeed  mov     [rsp+0B8h+var_38], rax
0x18004eef5  mov     rax, [rcx+270h]
0x18004eefc  mov     r14d, r9d
0x18004eeff  mov     r15, [rsp+0B8h+arg_28]
0x18004ef07  mov     r10, r8
0x18004ef0a  mov     r9d, [rsp+0B8h+arg_20]; unsigned int
0x18004ef12  mov     rdi, rdx
0x18004ef15  mov     rsi, rcx
0x18004ef18  mov     [rsp+0B8h+var_98], r15; struct IStream **
0x18004ef1d  mov     rbx, [rax+50h]
0x18004ef21  mov     r8d, r14d; unsigned int
0x18004ef24  xor     eax, eax
0x18004ef26  mov     rdx, r10; void *
0x18004ef29  mov     rcx, rdi; unsigned __int16 *
0x18004ef2c  mov     [rsp+0B8h+var_48], ax
0x18004ef31  call    ?OpenStream@CExpParameterValidate@@SAJPEBGPEAXKKPEAPEAUIStream@@@Z; CExpParameterValidate::OpenStream(ushort const *,void *,ulong,ulong,IStream * *)
0x18004ef36  test    eax, eax
0x18004ef38  js      loc_18004F075
0x18004ef3e  cmp     qword ptr [rsi+278h], 0
0x18004ef46  jz      short loc_18004EF52
0x18004ef48  mov     eax, 80030001h
0x18004ef4d  jmp     loc_18004F075
0x18004ef52  lea     eax, [r14-10h]
0x18004ef56  test    eax, 0FFFFFFFDh
0x18004ef5b  jz      short loc_18004EF67
0x18004ef5d  mov     eax, 800300FFh
0x18004ef62  jmp     loc_18004F075
0x18004ef67  cmp     dword ptr [rsi+288h], 10h
0x18004ef6e  jnz     short loc_18004EF80
0x18004ef70  cmp     r14d, 12h
0x18004ef74  jnz     short loc_18004EF80
0x18004ef76  mov     eax, 80030005h
0x18004ef7b  jmp     loc_18004F075
0x18004ef80  mov     rdx, rdi; unsigned __int16 *
0x18004ef83  lea     rcx, [rsp+0B8h+var_88]; this
0x18004ef88  call    ?Set@CDfName@@QEAAXPEBG@Z; CDfName::Set(ushort const *)
0x18004ef8d  test    rbx, rbx
0x18004ef90  jz      loc_18004F06E
0x18004ef96  mov     rdx, rbx; struct CDfName *
0x18004ef99  lea     rcx, [rsp+0B8h+var_88]; struct CDfName *
0x18004ef9e  call    ?NameCompare@CDirectory@@SAHPEBVCDfName@@0@Z; CDirectory::NameCompare(CDfName const *,CDfName const *)
0x18004efa3  test    eax, eax
0x18004efa5  jz      short loc_18004EFAD
0x18004efa7  mov     rbx, [rbx+50h]
0x18004efab  jmp     short loc_18004EF8D
0x18004efad  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18004efb4  xor     edx, edx; dwFlags
0x18004efb6  lea     r8d, [rdx+40h]; dwBytes
0x18004efba  call    cs:__imp_HeapAlloc
0x18004efc0  mov     rdi, rax
0x18004efc3  test    rax, rax
0x18004efc6  jz      loc_18004F067
0x18004efcc  mov     rcx, rax; this
0x18004efcf  call    ??0CSimpStream@@QEAA@XZ; CSimpStream::CSimpStream(void)
0x18004efd4  mov     qword ptr [rdi+30h], 0
0x18004efdc  lea     rax, ??_7CSimpStreamOpen@@6BIMarshal@@@; const CSimpStreamOpen::`vftable'{for `IMarshal'}
0x18004efe3  mov     [rdi+8], rax
0x18004efe7  lea     rcx, ??_7CSimpStreamOpen@@6BIStream@@@; const CSimpStreamOpen::`vftable'{for `IStream'}
0x18004efee  mov     [rdi], rcx
0x18004eff1  xor     r9d, r9d; dwMoveMethod
0x18004eff4  mov     rcx, [rsi+40h]; hFile
0x18004eff8  xor     r8d, r8d; lpDistanceToMoveHigh
0x18004effb  mov     [rsi+278h], rbx
0x18004f002  mov     ebp, [rbx+44h]
0x18004f005  inc     ebp
0x18004f007  mov     [rdi+30h], rbx
0x18004f00b  shl     ebp, 9
0x18004f00e  mov     edx, ebp; lDistanceToMove
0x18004f010  mov     [rdi+14h], ebp
0x18004f013  mov     [rdi+28h], rcx
0x18004f017  mov     [rdi+20h], rsi
0x18004f01b  mov     dword ptr [rdi+10h], 1
0x18004f022  mov     [rdi+38h], r14d
0x18004f026  call    cs:__imp_SetFilePointer
0x18004f02c  cmp     eax, 0FFFFFFFFh
0x18004f02f  jnz     short loc_18004F05D
0x18004f031  call    cs:__imp_GetLastError
0x18004f037  mov     ebx, eax
0x18004f039  test    eax, eax
0x18004f03b  jle     short loc_18004F046
0x18004f03d  movzx   ebx, ax
0x18004f040  or      ebx, 80070000h
0x18004f046  test    ebx, ebx
0x18004f048  jns     short loc_18004F062
0x18004f04a  mov     rcx, rdi; this
0x18004f04d  call    ??_GCSimpStreamOpen@@QEAAPEAXI@Z; CSimpStreamOpen::`scalar deleting destructor'(uint)
0x18004f052  xor     edi, edi
0x18004f054  mov     [rsi+278h], rdi
0x18004f05b  jmp     short loc_18004F062
0x18004f05d  mov     [rdi+18h], ebp
0x18004f060  xor     ebx, ebx
0x18004f062  mov     [r15], rdi
0x18004f065  jmp     short loc_18004F073
0x18004f067  mov     eax, 80030008h
0x18004f06c  jmp     short loc_18004F075
0x18004f06e  mov     ebx, 80030002h
0x18004f073  mov     eax, ebx
0x18004f075  mov     rcx, [rsp+0B8h+var_38]
0x18004f07d  xor     rcx, rsp; StackCookie
0x18004f080  call    __security_check_cookie
0x18004f085  mov     rbx, [rsp+0B8h+arg_10]
0x18004f08d  add     rsp, 90h
0x18004f094  pop     r15
0x18004f096  pop     r14
0x18004f098  pop     rdi
0x18004f099  pop     rsi
0x18004f09a  pop     rbp
0x18004f09b  retn
```
