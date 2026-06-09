# ATL::CComObject<ServerClassFactoryT<CProvisioningWapDPURemote>>::CreateInstance(ATL::CComObject<ServerClassFactoryT<CProvisioningWapDPURemote>> * *)

- ea: `0x140006b40`
- end: `0x140006c1d`
- name: `?CreateInstance@?$CComObject@V?$ServerClassFactoryT@VCProvisioningWapDPURemote@@@@@ATL@@SAJPEAPEAV12@@Z`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140006a80`

## callees

- `0x140001800`
- `0x140006b40`
- `0x140006ebc`
- `0x14000a010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<ServerClassFactoryT<CProvisioningWapDPURemote>>::CreateInstance(char **a1)
{
  char **v1; // rsi
  int v3; // edi
  char *v4; // rbx
  char *v6; // [rsp+50h] [rbp+18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  try
  {
    *a1 = 0;
    v3 = -2147024882;
    v4 = (char *)operator new(0x40u);
    *((_DWORD *)v4 + 2) = 0;
    *((_OWORD *)v4 + 1) = 0;
    *((_OWORD *)v4 + 2) = 0;
    *((_QWORD *)v4 + 6) = 0;
    v4[56] = 0;
    *(_QWORD *)v4 = &ATL::CComObject<ServerClassFactoryT<CProvisioningWapDPURemote>>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v6 = v4;
  }
  catch ( ... )
  {
    v1 = a1;
    v3 = -2147024882;
    v4 = v6;
  }
  if ( v4 )
  {
    v3 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v4 + 16));
    if ( v3 < 0 )
    {
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v4 + 40LL))(v4, 1);
      v4 = 0;
    }
    else
    {
      v4[56] = 1;
      v3 = 0;
    }
  }
  *v1 = v4;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140006b40  mov     [rsp+arg_18], rbx
0x140006b45  mov     [rsp+arg_0], rcx
0x140006b4a  push    rsi
0x140006b4b  push    rdi
0x140006b4c  push    r14
0x140006b4e  sub     rsp, 20h
0x140006b52  mov     rsi, rcx
0x140006b55  test    rcx, rcx
0x140006b58  jnz     short loc_140006B64
0x140006b5a  mov     eax, 80004003h
0x140006b5f  jmp     loc_140006C0E
0x140006b64  mov     qword ptr [rcx], 0
0x140006b6b  mov     edi, 8007000Eh
0x140006b70  mov     [rsp+38h+arg_8], edi
0x140006b74  mov     [rsp+38h+arg_10], 0
0x140006b7d  mov     ecx, 40h ; '@'; Size
0x140006b82  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140006b87  mov     rbx, rax
0x140006b8a  mov     dword ptr [rax+8], 0
0x140006b91  xorps   xmm0, xmm0
0x140006b94  xor     eax, eax
0x140006b96  movups  xmmword ptr [rbx+10h], xmm0
0x140006b9a  movups  xmmword ptr [rbx+20h], xmm0
0x140006b9e  mov     [rbx+30h], rax
0x140006ba2  mov     [rbx+38h], al
0x140006ba5  lea     rax, ??_7?$CComObject@V?$ServerClassFactoryT@VCProvisioningWapDPURemote@@@@@ATL@@6B@; const ATL::CComObject<ServerClassFactoryT<CProvisioningWapDPURemote>>::`vftable'
0x140006bac  mov     [rbx], rax
0x140006baf  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140006bb6  mov     rax, [rcx]
0x140006bb9  mov     rax, [rax+8]
0x140006bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006bc2  mov     [rsp+38h+arg_10], rbx
0x140006bc7  jmp     short loc_140006BD7
0x140006bc9  mov     rsi, [rsp+38h+arg_0]
0x140006bce  mov     edi, [rsp+38h+arg_8]
0x140006bd2  mov     rbx, [rsp+38h+arg_10]
0x140006bd7  test    rbx, rbx
0x140006bda  jz      short loc_140006C09
0x140006bdc  lea     rcx, [rbx+10h]; this
0x140006be0  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x140006be5  mov     edi, eax
0x140006be7  test    eax, eax
0x140006be9  js      short loc_140006BF3
0x140006beb  mov     byte ptr [rbx+38h], 1
0x140006bef  xor     edi, edi
0x140006bf1  jmp     short loc_140006C09
0x140006bf3  mov     rdx, [rbx]
0x140006bf6  mov     rax, [rdx+28h]
0x140006bfa  mov     edx, 1
0x140006bff  mov     rcx, rbx
0x140006c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c07  xor     ebx, ebx
0x140006c09  mov     [rsi], rbx
0x140006c0c  mov     eax, edi
0x140006c0e  mov     rbx, [rsp+38h+arg_18]
0x140006c13  add     rsp, 20h
0x140006c17  pop     r14
0x140006c19  pop     rdi
0x140006c1a  pop     rsi
0x140006c1b  retn
```
