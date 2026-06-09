# CSyncMLDPU::characters(ushort const *,int)

- ea: `0x18001d8e4`
- end: `0x18001da29`
- name: `?characters@CSyncMLDPU@@AEAAJPEBGH@Z`
- size: `325`
- prototype: `__int64 __fastcall(CSyncMLDPU *this, const unsigned __int16 *, signed int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007820`

## callees

- `0x1800011d4`
- `0x1800034d0`
- `0x18001bf2c`
- `0x18001d8e4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d9aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d9c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d9cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d9aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d9c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d9cf`
- `DMCmnUtils!CopyString` at `0x18001d950`
- `DMCmnUtils!CopyString` at `0x18001d950`
- `DMCmnUtils!BigStrcat` at `0x18001d988`
- `DMCmnUtils!BigStrcat` at `0x18001d988`

## pseudocode

```c
__int64 __fastcall CSyncMLDPU::characters(CSyncMLDPU *this, const unsigned __int16 *a2, signed int a3)
{
  int v3; // edi
  __int64 v5; // rdx
  unsigned __int16 *v6; // rsi
  int v7; // r8d
  int v8; // r9d
  CSyncMLCmd *v9; // rcx
  const unsigned __int16 *v11; // [rsp+30h] [rbp-10h] BYREF
  signed int v12; // [rsp+60h] [rbp+20h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+38h] BYREF

  v3 = 0;
  hMem = 0;
  if ( *((_DWORD *)this + 60) )
  {
    if ( (unsigned int)dword_18003E048 > 5 )
    {
      v11 = a2;
      v12 = a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        (_DWORD)this,
        (unsigned int)byte_1800361FB,
        a3,
        a3,
        (__int64)&v12,
        (__int64)&v11);
    }
  }
  else if ( a3 > 0 )
  {
    v3 = CopyString(a2, a3, (unsigned __int16 **)&hMem);
    if ( v3 >= 0 )
    {
      v5 = *((_QWORD *)this + 42);
      if ( v5 )
      {
        v6 = BigStrcat(2u, v5, hMem);
        if ( v6 )
        {
          LocalFree(*((HLOCAL *)this + 42));
          *((_QWORD *)this + 42) = v6;
        }
        else
        {
          v3 = -2147024882;
        }
      }
      else
      {
        *((_QWORD *)this + 42) = hMem;
        hMem = 0;
      }
    }
  }
  LocalFree(hMem);
  LocalFree(0);
  if ( v3 < 0 )
  {
    if ( (unsigned int)dword_18003E048 > 2 )
    {
      v12 = v3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18003E048,
        (unsigned int)word_180036192,
        v7,
        v8,
        (__int64)&v12);
    }
    v9 = (CSyncMLCmd *)*((_QWORD *)this + 8);
    if ( v9 )
      CSyncMLCmd::SetContextualParsingHresult(v9, v3);
  }
  return 0;
}

```

## disassembly

```asm
0x18001d8e4  mov     [rsp-18h+arg_8], rbx
0x18001d8e9  push    rbp
0x18001d8ea  push    rsi
0x18001d8eb  push    rdi
0x18001d8ec  mov     rbp, rsp
0x18001d8ef  sub     rsp, 40h
0x18001d8f3  xor     edi, edi
0x18001d8f5  mov     r9d, r8d
0x18001d8f8  mov     r10, rdx
0x18001d8fb  mov     rbx, rcx
0x18001d8fe  mov     [rbp+hMem], rdi
0x18001d902  cmp     [rcx+0F0h], edi
0x18001d908  jbe     short loc_18001D941
0x18001d90a  mov     eax, cs:dword_18003E048
0x18001d910  cmp     eax, 5
0x18001d913  jbe     loc_18001D9BD
0x18001d919  lea     rax, [rbp+var_10]
0x18001d91d  mov     [rbp+var_10], rdx
0x18001d921  mov     [rsp+40h+var_18], rax
0x18001d926  lea     rdx, byte_1800361FB
0x18001d92d  lea     rax, [rbp+arg_0]
0x18001d931  mov     [rbp+arg_0], r8d
0x18001d935  mov     [rsp+40h+var_20], rax
0x18001d93a  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18001d93f  jmp     short loc_18001D9BD
0x18001d941  test    r9d, r9d
0x18001d944  jle     short loc_18001D9BD
0x18001d946  lea     r8, [rbp+hMem]
0x18001d94a  mov     edx, r9d
0x18001d94d  mov     rcx, r10
0x18001d950  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18001d957  nop     dword ptr [rax+rax+00h]
0x18001d95c  mov     edi, eax
0x18001d95e  test    eax, eax
0x18001d960  js      short loc_18001D9BD
0x18001d962  mov     rdx, [rbx+150h]
0x18001d969  test    rdx, rdx
0x18001d96c  jnz     short loc_18001D97F
0x18001d96e  mov     rcx, [rbp+hMem]
0x18001d972  mov     [rbx+150h], rcx
0x18001d979  mov     [rbp+hMem], rdx
0x18001d97d  jmp     short loc_18001D9BD
0x18001d97f  mov     r8, [rbp+hMem]
0x18001d983  mov     ecx, 2
0x18001d988  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x18001d98f  nop     dword ptr [rax+rax+00h]
0x18001d994  mov     rsi, rax
0x18001d997  test    rax, rax
0x18001d99a  jnz     short loc_18001D9A3
0x18001d99c  mov     edi, 8007000Eh
0x18001d9a1  jmp     short loc_18001D9BD
0x18001d9a3  mov     rcx, [rbx+150h]; hMem
0x18001d9aa  call    cs:__imp_LocalFree
0x18001d9b1  nop     dword ptr [rax+rax+00h]
0x18001d9b6  mov     [rbx+150h], rsi
0x18001d9bd  mov     rcx, [rbp+hMem]; hMem
0x18001d9c1  call    cs:__imp_LocalFree
0x18001d9c8  nop     dword ptr [rax+rax+00h]
0x18001d9cd  xor     ecx, ecx; hMem
0x18001d9cf  call    cs:__imp_LocalFree
0x18001d9d6  nop     dword ptr [rax+rax+00h]
0x18001d9db  test    edi, edi
0x18001d9dd  jns     short loc_18001DA19
0x18001d9df  mov     eax, cs:dword_18003E048
0x18001d9e5  cmp     eax, 2
0x18001d9e8  jbe     short loc_18001DA09
0x18001d9ea  lea     rax, [rbp+arg_0]
0x18001d9ee  mov     [rbp+arg_0], edi
0x18001d9f1  lea     rdx, word_180036192
0x18001d9f8  mov     [rsp+40h+var_20], rax
0x18001d9fd  lea     rcx, dword_18003E048
0x18001da04  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001da09  mov     rcx, [rbx+40h]; this
0x18001da0d  test    rcx, rcx
0x18001da10  jz      short loc_18001DA19
0x18001da12  mov     edx, edi; int
0x18001da14  call    ?SetContextualParsingHresult@CSyncMLCmd@@QEAAXJ@Z; CSyncMLCmd::SetContextualParsingHresult(long)
0x18001da19  mov     rbx, [rsp+40h+arg_8]
0x18001da1e  xor     eax, eax
0x18001da20  add     rsp, 40h
0x18001da24  pop     rdi
0x18001da25  pop     rsi
0x18001da26  pop     rbp
0x18001da27  retn
```
