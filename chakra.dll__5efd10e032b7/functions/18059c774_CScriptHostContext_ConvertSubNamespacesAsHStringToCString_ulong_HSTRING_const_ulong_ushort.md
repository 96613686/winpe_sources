# CScriptHostContext::ConvertSubNamespacesAsHStringToCString(ulong,HSTRING__ * const *,ulong *,ushort * * *)

- ea: `0x18059c774`
- end: `0x18059c8ad`
- name: `?ConvertSubNamespacesAsHStringToCString@CScriptHostContext@@CAJKPEBQEAUHSTRING__@@PEAKPEAPEAPEAG@Z`
- size: `313`
- prototype: `__int64 __fastcall(unsigned int, HSTRING *, unsigned int *, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18059cc10`

## callees

- `0x180401df0`
- `0x18059c774`
- `0x18059c8b4`
- `0x18059cb58`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18059c812`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18059c812`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18059c83a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18059c89f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18059c83a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18059c89f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18059c7b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18059c7b2`

## pseudocode

```c
__int64 __fastcall CScriptHostContext::ConvertSubNamespacesAsHStringToCString(
        unsigned int a1,
        HSTRING *a2,
        unsigned int *a3,
        unsigned __int16 ***a4)
{
  SIZE_T v5; // rdi
  unsigned __int16 **v6; // rax
  unsigned __int16 **v7; // r14
  unsigned int v8; // ebx
  SIZE_T i; // rcx
  __int64 v10; // rdi
  HSTRING v11; // rcx
  PCWSTR StringRawBuffer; // rax
  int v13; // eax
  LPVOID pv; // [rsp+20h] [rbp-20h] BYREF
  unsigned int v16; // [rsp+28h] [rbp-18h] BYREF
  unsigned __int16 **v17; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]

  v16 = 0;
  v5 = 8LL * a1;
  v17 = 0;
  v6 = (unsigned __int16 **)CoTaskMemAlloc(v5);
  v7 = v6;
  if ( v6 )
  {
    v8 = 0;
    for ( i = v5; i; --i )
    {
      *(_BYTE *)v6 = 0;
      v6 = (unsigned __int16 **)((char *)v6 + 1);
    }
    AutoDeepArray<unsigned short *,unsigned long,&void CoTaskMemFreeDeallocate<unsigned short * *>(unsigned short * *),&void CoTaskMemFreeDeallocate<unsigned short *>(unsigned short *)>::Deallocate(&v16);
    v17 = v7;
    v16 = a1;
    if ( v5 && (v10 = 0, a1) )
    {
      while ( 1 )
      {
        v11 = a2[v10];
        pv = 0;
        StringRawBuffer = WindowsGetStringRawBuffer(v11, 0);
        v13 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoCoTaskMemStringAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoCoTaskMemStringDeallocate(unsigned short *)>::CopyFromString(
                &pv,
                StringRawBuffer);
        v8 = v13;
        if ( v13 < 0 )
          break;
        v7[v10] = (unsigned __int16 *)pv;
        CoTaskMemFree(0);
        v10 = (unsigned int)(v10 + 1);
        if ( (unsigned int)v10 >= a1 )
          goto LABEL_9;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x17D,
        (unsigned int)"onecoreuap\\inetcore\\lib\\scriptprojectionhost\\scripthostcontext.cxx",
        (const char *)(unsigned int)v13,
        (int)pv);
      CoTaskMemFree(pv);
    }
    else
    {
LABEL_9:
      v16 = 0;
      v17 = 0;
      *a3 = a1;
      *a4 = v7;
    }
  }
  else
  {
    v8 = -2147024882;
  }
  AutoDeepArray<unsigned short *,unsigned long,&void CoTaskMemFreeDeallocate<unsigned short * *>(unsigned short * *),&void CoTaskMemFreeDeallocate<unsigned short *>(unsigned short *)>::Deallocate(&v16);
  return v8;
}

```

## disassembly

```asm
0x18059c774  mov     rax, rsp
0x18059c777  mov     [rax+20h], r9
0x18059c77b  mov     [rax+18h], r8
0x18059c77f  mov     [rax+10h], rdx
0x18059c783  mov     [rax+8], ecx
0x18059c786  push    rbp
0x18059c787  push    rbx
0x18059c788  push    rsi
0x18059c789  push    rdi
0x18059c78a  push    r12
0x18059c78c  push    r14
0x18059c78e  push    r15
0x18059c790  mov     rbp, rsp
0x18059c793  sub     rsp, 40h
0x18059c797  mov     esi, [rbp+arg_0]
0x18059c79a  mov     edi, esi
0x18059c79c  mov     [rbp+var_18], 0
0x18059c7a3  shl     rdi, 3
0x18059c7a7  mov     rcx, rdi; cb
0x18059c7aa  mov     [rbp+var_10], 0
0x18059c7b2  call    cs:__imp_CoTaskMemAlloc
0x18059c7b9  nop     dword ptr [rax+rax+00h]
0x18059c7be  mov     r14, rax
0x18059c7c1  test    rax, rax
0x18059c7c4  jnz     short loc_18059C7D0
0x18059c7c6  mov     ebx, 8007000Eh
0x18059c7cb  jmp     loc_18059C868
0x18059c7d0  xor     ebx, ebx
0x18059c7d2  mov     rcx, rdi
0x18059c7d5  test    rdi, rdi
0x18059c7d8  jz      short loc_18059C7E5
0x18059c7da  mov     [rax], bl
0x18059c7dc  inc     rax
0x18059c7df  sub     rcx, 1
0x18059c7e3  jnz     short loc_18059C7DA
0x18059c7e5  lea     rcx, [rbp+var_18]
0x18059c7e9  call    ?Deallocate@?$AutoDeepArray@PEAGK$1??$CoTaskMemFreeDeallocate@PEAPEAG@@YAXPEAPEAG@Z$1??$CoTaskMemFreeDeallocate@PEAG@@YAXPEAG@Z@@QEAAXXZ; AutoDeepArray<ushort *,ulong,&CoTaskMemFreeDeallocate<ushort * *>(ushort * *),&CoTaskMemFreeDeallocate<ushort *>(ushort *)>::Deallocate(void)
0x18059c7ee  mov     [rbp+var_10], r14
0x18059c7f2  mov     [rbp+var_18], esi
0x18059c7f5  test    rdi, rdi
0x18059c7f8  jz      short loc_18059C84C
0x18059c7fa  mov     r12, [rbp+arg_8]
0x18059c7fe  xor     edi, edi
0x18059c800  test    esi, esi
0x18059c802  jz      short loc_18059C84C
0x18059c804  mov     rcx, [r12+rdi*8]; string
0x18059c808  xor     edx, edx; length
0x18059c80a  mov     [rbp+pv], 0
0x18059c812  call    cs:__imp_WindowsGetStringRawBuffer
0x18059c819  nop     dword ptr [rax+rax+00h]
0x18059c81e  mov     rdx, rax
0x18059c821  lea     rcx, [rbp+pv]
0x18059c825  call    ?CopyFromString@?$AutoStringWithAllocator@G$1?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoCoTaskMemStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJPEBG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint),&Common::AutoCoTaskMemStringDeallocate(ushort *)>::CopyFromString(ushort const *)
0x18059c82a  mov     ebx, eax
0x18059c82c  test    eax, eax
0x18059c82e  js      short loc_18059C883
0x18059c830  mov     rcx, [rbp+pv]
0x18059c834  mov     [r14+rdi*8], rcx
0x18059c838  xor     ecx, ecx; pv
0x18059c83a  call    cs:__imp_CoTaskMemFree
0x18059c841  nop     dword ptr [rax+rax+00h]
0x18059c846  inc     edi
0x18059c848  cmp     edi, esi
0x18059c84a  jb      short loc_18059C804
0x18059c84c  mov     rax, [rbp+arg_10]
0x18059c850  mov     [rbp+var_18], 0
0x18059c857  mov     [rbp+var_10], 0
0x18059c85f  mov     [rax], esi
0x18059c861  mov     rax, [rbp+arg_18]
0x18059c865  mov     [rax], r14
0x18059c868  lea     rcx, [rbp+var_18]
0x18059c86c  call    ?Deallocate@?$AutoDeepArray@PEAGK$1??$CoTaskMemFreeDeallocate@PEAPEAG@@YAXPEAPEAG@Z$1??$CoTaskMemFreeDeallocate@PEAG@@YAXPEAG@Z@@QEAAXXZ; AutoDeepArray<ushort *,ulong,&CoTaskMemFreeDeallocate<ushort * *>(ushort * *),&CoTaskMemFreeDeallocate<ushort *>(ushort *)>::Deallocate(void)
0x18059c871  mov     eax, ebx
0x18059c873  add     rsp, 40h
0x18059c877  pop     r15
0x18059c879  pop     r14
0x18059c87b  pop     r12
0x18059c87d  pop     rdi
0x18059c87e  pop     rsi
0x18059c87f  pop     rbx
0x18059c880  pop     rbp
0x18059c881  retn
0x18059c883  mov     rcx, [rbp+38h]; this
0x18059c887  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\lib\\scriptprojec"...
0x18059c88e  mov     r9d, eax; char *
0x18059c891  mov     edx, 17Dh; void *
0x18059c896  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18059c89b  mov     rcx, [rbp+pv]; pv
0x18059c89f  call    cs:__imp_CoTaskMemFree
0x18059c8a6  nop     dword ptr [rax+rax+00h]
0x18059c8ab  jmp     short loc_18059C868
```
