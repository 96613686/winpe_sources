# SspTelemetry::ClientImageInfo::GetSvchostServiceTag(void)

- ea: `0x180012fd0`
- end: `0x1800131bd`
- name: `?GetSvchostServiceTag@ClientImageInfo@SspTelemetry@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `493`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180009b00`
- `0x180011fc4`
- `0x18002d4cc`
- `0x180051944`
- `0x180052f18`
- `0x1800532a0`
- `0x1800581a8`
- `0x1800587c8`
- `0x180059760`
- `0x180068748`

## callees

- `0x180012fd0`
- `0x18002eda4`
- `0x18002f064`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180012ffe`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180012ffe`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800130fb`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180013178`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800130fb`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180013178`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013105`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001311b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013153`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013184`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013193`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800131a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800131b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013105`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001311b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013153`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013184`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013193`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800131a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800131b1`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x180013050`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x18001307c`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x180013050`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x18001307c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall SspTelemetry::ClientImageInfo::GetSvchostServiceTag(__int64 a1, _QWORD *a2)
{
  unsigned __int64 v5; // rdx
  unsigned __int64 v6; // rdx
  HLOCAL v7; // rsi
  __int64 v8; // rdi
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // r14
  void *v12; // rax
  void *v13; // rbp
  __int64 v14; // rax
  __int64 v15; // rdi
  void *v16; // rax
  void *v17; // rsi
  _DWORD v18[2]; // [rsp+20h] [rbp-48h] BYREF
  HLOCAL hMem; // [rsp+28h] [rbp-40h]
  __int128 v20; // [rsp+30h] [rbp-38h] BYREF
  HLOCAL v21; // [rsp+40h] [rbp-28h]

  *a2 = 0;
  if ( !(unsigned int)_o__wcsnicmp(a1 + 32, L"svchost", 7) )
  {
    v20 = 0;
    v21 = 0;
    LODWORD(v20) = *(_DWORD *)(a1 + 8);
    DWORD1(v20) = NtCurrentTeb()->SubProcessTag;
    if ( (unsigned int)I_QueryTagInformation(0, 1, &v20) )
    {
      v18[1] = 0;
      hMem = 0;
      v18[0] = *(_DWORD *)(a1 + 8);
      if ( !(unsigned int)I_QueryTagInformation(0, 3, v18) )
      {
        v7 = hMem;
        if ( hMem )
        {
          if ( *(_DWORD *)hMem == 1
            && (v8 = *((_QWORD *)hMem + 1), *(_DWORD *)v8 == 1)
            && (v9 = *(_QWORD *)(v8 + 8)) != 0 )
          {
            v10 = -1;
            do
              ++v10;
            while ( *(_WORD *)(v9 + 2 * v10) );
            v11 = v10 + 1;
            v12 = SspTelemetry::TelemetryAllocate((SspTelemetry *)(2 * (v10 + 1)), v6);
            v13 = v12;
            if ( v12 )
            {
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                a2,
                v12);
              _o_wcsncpy_s(v13, v11);
            }
            LocalFree(v7);
          }
          else
          {
            LocalFree(hMem);
          }
        }
      }
    }
    else if ( v21 )
    {
      v14 = -1;
      do
        ++v14;
      while ( *((_WORD *)v21 + v14) );
      v15 = v14 + 1;
      v16 = SspTelemetry::TelemetryAllocate((SspTelemetry *)(2 * (v14 + 1)), v5);
      v17 = v16;
      if ( v16 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          a2,
          v16);
        _o_wcsncpy_s(v17, v15);
      }
      LocalFree(v21);
    }
    else
    {
      LocalFree(0);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180012fd0  mov     [rsp+arg_8], rbx
0x180012fd5  mov     [rsp+arg_10], rbp
0x180012fda  push    rsi
0x180012fdb  push    rdi
0x180012fdc  push    r14
0x180012fde  sub     rsp, 50h
0x180012fe2  mov     rbx, rdx
0x180012fe5  mov     rdi, rcx
0x180012fe8  xor     eax, eax
0x180012fea  mov     [rdx], rax
0x180012fed  add     rcx, 20h ; ' '
0x180012ff1  mov     r8d, 7
0x180012ff7  lea     rdx, aSvchost; "svchost"
0x180012ffe  call    cs:__imp__o__wcsnicmp
0x180013004  test    eax, eax
0x180013006  jz      short loc_180013021
0x180013008  mov     rax, rbx
0x18001300b  mov     rbx, [rsp+68h+arg_8]
0x180013010  mov     rbp, [rsp+68h+arg_10]
0x180013018  add     rsp, 50h
0x18001301c  pop     r14
0x18001301e  pop     rdi
0x18001301f  pop     rsi
0x180013020  retn
0x180013021  xorps   xmm0, xmm0
0x180013024  xor     eax, eax
0x180013026  movups  [rsp+68h+var_38], xmm0
0x18001302b  mov     [rsp+68h+var_28], rax
0x180013030  mov     eax, [rdi+8]
0x180013033  mov     dword ptr [rsp+68h+var_38], eax
0x180013037  mov     rax, gs:1720h
0x180013040  mov     dword ptr [rsp+68h+var_38+4], eax
0x180013044  lea     r8, [rsp+68h+var_38]
0x180013049  mov     edx, 1
0x18001304e  xor     ecx, ecx
0x180013050  call    cs:__imp_I_QueryTagInformation
0x180013056  test    eax, eax
0x180013058  jz      loc_180013111
0x18001305e  xor     eax, eax
0x180013060  mov     [rsp+68h+var_44], eax
0x180013064  mov     [rsp+68h+hMem], rax
0x180013069  mov     eax, [rdi+8]
0x18001306c  mov     [rsp+68h+var_48], eax
0x180013070  lea     r8, [rsp+68h+var_48]
0x180013075  mov     edx, 3
0x18001307a  xor     ecx, ecx
0x18001307c  call    cs:__imp_I_QueryTagInformation
0x180013082  test    eax, eax
0x180013084  jnz     short loc_180013008
0x180013086  mov     rsi, [rsp+68h+hMem]
0x18001308b  test    rsi, rsi
0x18001308e  jz      loc_180013008
0x180013094  cmp     dword ptr [rsi], 1
0x180013097  jnz     loc_180013190
0x18001309d  mov     rdi, [rsi+8]
0x1800130a1  cmp     dword ptr [rdi], 1
0x1800130a4  jnz     loc_1800131AE
0x1800130aa  mov     rdi, [rdi+8]
0x1800130ae  test    rdi, rdi
0x1800130b1  jz      loc_1800131AE
0x1800130b7  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800130be  xchg    ax, ax
0x1800130c0  lea     rax, [rax+1]
0x1800130c4  cmp     word ptr [rdi+rax*2], 0
0x1800130c9  jnz     short loc_1800130C0
0x1800130cb  lea     r14, [rax+1]
0x1800130cf  lea     rcx, [r14+r14]; this
0x1800130d3  call    ?TelemetryAllocate@SspTelemetry@@YAPEAX_K@Z; SspTelemetry::TelemetryAllocate(unsigned __int64)
0x1800130d8  mov     rbp, rax
0x1800130db  test    rax, rax
0x1800130de  jz      loc_18001319F
0x1800130e4  mov     rdx, rax
0x1800130e7  mov     rcx, rbx
0x1800130ea  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800130ef  mov     r9, r14
0x1800130f2  mov     r8, rdi
0x1800130f5  mov     rdx, r14
0x1800130f8  mov     rcx, rbp
0x1800130fb  call    cs:__imp__o_wcsncpy_s
0x180013101  nop
0x180013102  mov     rcx, rsi; hMem
0x180013105  call    cs:__imp_LocalFree
0x18001310b  nop
0x18001310c  jmp     loc_180013008
0x180013111  mov     rcx, [rsp+68h+var_28]; hMem
0x180013116  test    rcx, rcx
0x180013119  jnz     short loc_180013127
0x18001311b  call    cs:__imp_LocalFree
0x180013121  nop
0x180013122  jmp     loc_180013008
0x180013127  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001312e  lea     rax, [rax+1]
0x180013132  cmp     word ptr [rcx+rax*2], 0
0x180013137  jnz     short loc_18001312E
0x180013139  lea     rdi, [rax+1]
0x18001313d  lea     rcx, [rdi+rdi]; this
0x180013141  call    ?TelemetryAllocate@SspTelemetry@@YAPEAX_K@Z; SspTelemetry::TelemetryAllocate(unsigned __int64)
0x180013146  mov     rsi, rax
0x180013149  test    rax, rax
0x18001314c  jnz     short loc_18001315F
0x18001314e  mov     rcx, [rsp+68h+var_28]; hMem
0x180013153  call    cs:__imp_LocalFree
0x180013159  nop
0x18001315a  jmp     loc_180013008
0x18001315f  mov     rdx, rsi
0x180013162  mov     rcx, rbx
0x180013165  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001316a  mov     r9, rdi
0x18001316d  mov     r8, [rsp+68h+var_28]
0x180013172  mov     rdx, rdi
0x180013175  mov     rcx, rsi
0x180013178  call    cs:__imp__o_wcsncpy_s
0x18001317e  nop
0x18001317f  mov     rcx, [rsp+68h+var_28]; hMem
0x180013184  call    cs:__imp_LocalFree
0x18001318a  nop
0x18001318b  jmp     loc_180013008
0x180013190  mov     rcx, rsi; hMem
0x180013193  call    cs:__imp_LocalFree
0x180013199  nop
0x18001319a  jmp     loc_180013008
0x18001319f  mov     rcx, rsi; hMem
0x1800131a2  call    cs:__imp_LocalFree
0x1800131a8  nop
0x1800131a9  jmp     loc_180013008
0x1800131ae  mov     rcx, rsi; hMem
0x1800131b1  call    cs:__imp_LocalFree
0x1800131b7  nop
0x1800131b8  jmp     loc_180013008
```
