# HttpWebRequest::ReadData(int)

- ea: `0x140028df0`
- end: `0x140028f26`
- name: `?ReadData@HttpWebRequest@@MEAAXH@Z`
- size: `310`
- prototype: `void(HttpWebRequest *__hidden this, int)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x140002814`
- `0x1400054e8`
- `0x14000caac`
- `0x1400111f4`
- `0x1400140c4`
- `0x140023430`
- `0x140028df0`
- `0x14002c3e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028ede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028ede`
- `WINHTTP!WinHttpReadData` at `0x140028e93`
- `WINHTTP!WinHttpReadData` at `0x140028e93`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall HttpWebRequest::ReadData(HttpWebRequest *this, DWORD a2)
{
  _QWORD *v4; // rbx
  __int64 v5; // r8
  char *v6; // r14
  int v7; // esi
  int v8; // eax
  char *v9; // rax
  size_t v10; // rdi
  _QWORD *v11; // rbx
  DWORD LastError; // eax
  _BYTE pExceptionObject[72]; // [rsp+20h] [rbp-48h] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+70h] [rbp+8h] BYREF
  char v15; // [rsp+78h] [rbp+10h] BYREF
  __int64 v16; // [rsp+80h] [rbp+18h] BYREF

  v4 = (_QWORD *)((char *)this + 48);
  v5 = *((_QWORD *)this + 6);
  v6 = (char *)*((_QWORD *)this + 7);
  v7 = (_DWORD)v6 - v5;
  v8 = (_DWORD)v6 - v5 + a2;
  if ( v8 > 10485760 )
  {
    Exception::Exception((Exception *)pExceptionObject, -895418332);
    throw (Exception *)pExceptionObject;
  }
  v15 = 0;
  if ( v8 >= (unsigned __int64)&v6[-v5] )
  {
    if ( v8 <= (unsigned __int64)&v6[-v5] )
      goto LABEL_9;
    if ( v8 > (unsigned __int64)(*((_QWORD *)this + 8) - v5) )
    {
      std::vector<unsigned char>::_Resize_reallocate<unsigned char>((char *)this + 48, v8, &v15);
      goto LABEL_9;
    }
    v10 = v8 - (_QWORD)&v6[-v5];
    memset_0(v6, 0, v10);
    v9 = &v6[v10];
  }
  else
  {
    v9 = (char *)(v8 + v5);
  }
  v4[1] = v9;
LABEL_9:
  dwNumberOfBytesRead = 0;
  if ( !WinHttpReadData(*((HINTERNET *)this + 20), (LPVOID)(*v4 + v7), a2, &dwNumberOfBytesRead) )
  {
    v11 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &v16,
            (__int64)&dword_14003353C);
    LastError = GetLastError();
    HttpException::HttpException(pExceptionObject, LastError, v11);
    throw (HttpException *)pExceptionObject;
  }
  std::vector<unsigned char>::resize(v4, v7 + dwNumberOfBytesRead);
  _InterlockedExchange((volatile __int32 *)this + 22, 10);
}

```

## disassembly

```asm
0x140028df0  mov     [rsp+arg_18], rbx
0x140028df5  push    rbp
0x140028df6  push    rsi
0x140028df7  push    rdi
0x140028df8  push    r14
0x140028dfa  push    r15
0x140028dfc  sub     rsp, 40h
0x140028e00  mov     r15d, edx
0x140028e03  mov     rbp, rcx
0x140028e06  lea     rbx, [rcx+30h]
0x140028e0a  mov     r8, [rbx]
0x140028e0d  mov     r14, [rbx+8]
0x140028e11  mov     esi, r14d
0x140028e14  sub     esi, r8d
0x140028e17  lea     eax, [rsi+rdx]
0x140028e1a  cmp     eax, 0A00000h
0x140028e1f  jg      loc_140028F05
0x140028e25  mov     [rsp+68h+arg_8], 0
0x140028e2a  mov     rcx, r14
0x140028e2d  sub     rcx, r8
0x140028e30  movsxd  rdi, eax
0x140028e33  cmp     rdi, rcx
0x140028e36  jnb     short loc_140028E3E
0x140028e38  lea     rax, [rdi+r8]
0x140028e3c  jmp     short loc_140028E72
0x140028e3e  jbe     short loc_140028E76
0x140028e40  mov     rax, [rbx+10h]
0x140028e44  sub     rax, r8
0x140028e47  cmp     rdi, rax
0x140028e4a  jbe     short loc_140028E5E
0x140028e4c  lea     r8, [rsp+68h+arg_8]
0x140028e51  mov     rdx, rdi
0x140028e54  mov     rcx, rbx
0x140028e57  call    ??$_Resize_reallocate@E@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBE@Z; std::vector<uchar>::_Resize_reallocate<uchar>(unsigned __int64,uchar const &)
0x140028e5c  jmp     short loc_140028E76
0x140028e5e  sub     rdi, rcx
0x140028e61  mov     r8, rdi; Size
0x140028e64  xor     edx, edx; Val
0x140028e66  mov     rcx, r14; void *
0x140028e69  call    memset_0
0x140028e6e  lea     rax, [rdi+r14]
0x140028e72  mov     [rbx+8], rax
0x140028e76  mov     [rsp+68h+dwNumberOfBytesRead], 0
0x140028e7e  movsxd  rdx, esi
0x140028e81  add     rdx, [rbx]; lpBuffer
0x140028e84  lea     r9, [rsp+68h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x140028e89  mov     r8d, r15d; dwNumberOfBytesToRead
0x140028e8c  mov     rcx, [rbp+0A0h]; hRequest
0x140028e93  call    cs:__imp_WinHttpReadData
0x140028e99  test    eax, eax
0x140028e9b  jz      short loc_140028EC7
0x140028e9d  mov     edx, [rsp+68h+dwNumberOfBytesRead]
0x140028ea1  add     edx, esi
0x140028ea3  mov     rcx, rbx
0x140028ea6  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x140028eab  mov     eax, 0Ah
0x140028eb0  xchg    eax, [rbp+58h]
0x140028eb3  mov     rbx, [rsp+68h+arg_18]
0x140028ebb  add     rsp, 40h
0x140028ebf  pop     r15
0x140028ec1  pop     r14
0x140028ec3  pop     rdi
0x140028ec4  pop     rsi
0x140028ec5  pop     rbp
0x140028ec6  retn
0x140028ec7  lea     rdx, dword_14003353C
0x140028ece  lea     rcx, [rsp+68h+arg_10]
0x140028ed6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140028edb  mov     rbx, rax
0x140028ede  call    cs:__imp_GetLastError
0x140028ee4  mov     r8, rbx
0x140028ee7  mov     edx, eax
0x140028ee9  lea     rcx, [rsp+68h+pExceptionObject]
0x140028eee  call    ??0HttpException@@QEAA@KAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; HttpException::HttpException(ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140028ef3  lea     rdx, _TI2?AVHttpException@@; pThrowInfo
0x140028efa  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x140028eff  call    _CxxThrowException_0
0x140028f05  mov     edx, 0CAA10024h; unsigned int
0x140028f0a  lea     rcx, [rsp+68h+pExceptionObject]; this
0x140028f0f  call    ??0Exception@@QEAA@K@Z; Exception::Exception(ulong)
0x140028f14  lea     rdx, _TI1?AVException@@; pThrowInfo
0x140028f1b  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x140028f20  call    _CxxThrowException_0
```
