# W3_CGI_HANDLER::SetCgiStateDoneWithRequest(void)

- ea: `0x180005914`
- end: `0x180005a4e`
- name: `?SetCgiStateDoneWithRequest@W3_CGI_HANDLER@@QEAAJXZ`
- size: `314`
- prototype: `__int64 __fastcall(W3_CGI_HANDLER *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000325c`
- `0x18000337c`
- `0x180004678`
- `0x1800047f0`
- `0x180004e50`

## callees

- `0x180005914`
- `0x180008010`

## pseudocode

```c
__int64 __fastcall W3_CGI_HANDLER::SetCgiStateDoneWithRequest(W3_CGI_HANDLER *this)
{
  __int64 v2; // rcx
  __int64 *v3; // rax
  __int64 *v4; // rdi
  int (__fastcall **v5)(__int64 *, GUID **); // rcx
  __int64 v6; // rax
  void (__fastcall *v7)(__int64 *, _QWORD *); // rax
  GUID *v9; // [rsp+20h] [rbp-59h] BYREF
  __int128 v10; // [rsp+28h] [rbp-51h]
  int v11; // [rsp+38h] [rbp-41h]
  __int64 v12; // [rsp+40h] [rbp-39h]
  _QWORD v13[6]; // [rsp+50h] [rbp-29h] BYREF
  __int128 v14; // [rsp+80h] [rbp+7h]
  int v15; // [rsp+90h] [rbp+17h]
  int v16; // [rsp+94h] [rbp+1Bh]
  __int64 v17; // [rsp+98h] [rbp+1Fh]
  GUID **v18; // [rsp+A0h] [rbp+27h]

  *((_DWORD *)this + 2) = 4;
  v2 = *((_QWORD *)this + 6);
  if ( v2 )
  {
    v3 = (__int64 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 272LL))(v2);
    v4 = v3;
    if ( v3 )
    {
      v5 = (int (__fastcall **)(__int64 *, GUID **))*v3;
      v9 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v10 = 0;
      if ( (*v5)(v3, &v9) >= 0 && DWORD2(v10) && ((_DWORD)v10 == 32 || (v10 & 0x20) != 0) && !*((_DWORD *)this + 2100) )
      {
        v13[1] = 32;
        *((_DWORD *)this + 2100) = 1;
        v13[2] = &`IISCGIEvents::GetAreaGuid'::`2'::AreaGuid;
        v17 = 1;
        v13[4] = L"CGI_END";
        v13[5] = 1;
        v9 = (GUID *)L"ContextId";
        v18 = &v9;
        v6 = *v4;
        v16 = 1;
        v13[3] = 2;
        v13[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
        v7 = *(void (__fastcall **)(__int64 *, _QWORD *))(v6 + 16);
        v14 = 0;
        v15 = 0;
        LODWORD(v10) = 72;
        *((_QWORD *)&v10 + 1) = 0;
        v11 = 16;
        v12 = 0;
        v7(v4, v13);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180005914  push    rbp
0x180005916  push    rbx
0x180005917  push    rdi
0x180005918  push    r14
0x18000591a  lea     rbp, [rsp-3Fh]
0x18000591f  sub     rsp, 0B8h
0x180005926  mov     rbx, rcx
0x180005929  mov     dword ptr [rcx+8], 4
0x180005930  mov     rcx, [rcx+30h]
0x180005934  test    rcx, rcx
0x180005937  jz      loc_180005A3F
0x18000593d  mov     rax, [rcx]
0x180005940  mov     rax, [rax+110h]
0x180005947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000594c  mov     rdi, rax
0x18000594f  test    rax, rax
0x180005952  jz      loc_180005A3F
0x180005958  mov     rcx, [rax]
0x18000595b  lea     r14, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180005962  xorps   xmm0, xmm0
0x180005965  mov     [rbp+57h+var_B0], r14
0x180005969  lea     rdx, [rbp+57h+var_B0]
0x18000596d  movdqu  [rbp+57h+var_A8], xmm0
0x180005972  mov     rax, [rcx]
0x180005975  mov     rcx, rdi
0x180005978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000597d  test    eax, eax
0x18000597f  js      loc_180005A3F
0x180005985  cmp     dword ptr [rbp+57h+var_A8+8], 0
0x180005989  jz      loc_180005A3F
0x18000598f  cmp     dword ptr [rbp+57h+var_A8], 20h ; ' '
0x180005993  jz      short loc_18000599F
0x180005995  test    byte ptr [rbp+57h+var_A8], 20h
0x180005999  jz      loc_180005A3F
0x18000599f  cmp     dword ptr [rbx+20D0h], 0
0x1800059a6  jnz     loc_180005A3F
0x1800059ac  mov     ecx, 1
0x1800059b1  mov     [rbp+57h+var_78], 20h ; ' '
0x1800059b9  mov     [rbx+20D0h], ecx
0x1800059bf  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISCGIEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISCGIEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x1800059c6  mov     [rbp+57h+var_70], rax
0x1800059ca  lea     rdx, [rbp+57h+var_80]
0x1800059ce  lea     rax, aCgiEnd; "CGI_END"
0x1800059d5  mov     [rbp+57h+var_38], rcx
0x1800059d9  mov     [rbp+57h+var_60], rax
0x1800059dd  xorps   xmm0, xmm0
0x1800059e0  lea     rax, aContextid; "ContextId"
0x1800059e7  mov     [rbp+57h+var_58], rcx
0x1800059eb  mov     [rbp+57h+var_B0], rax
0x1800059ef  lea     rax, [rbp+57h+var_B0]
0x1800059f3  mov     [rbp+57h+var_30], rax
0x1800059f7  mov     rax, [rdi]
0x1800059fa  mov     [rbp+57h+var_3C], ecx
0x1800059fd  mov     rcx, rdi
0x180005a00  mov     [rbp+57h+var_68], 2
0x180005a08  mov     [rbp+57h+var_80], r14
0x180005a0c  mov     rax, [rax+10h]
0x180005a10  movdqa  [rbp+57h+var_50], xmm0
0x180005a15  mov     [rbp+57h+var_40], 0
0x180005a1c  mov     dword ptr [rbp+57h+var_A8], 48h ; 'H'
0x180005a23  mov     qword ptr [rbp+57h+var_A8+8], 0
0x180005a2b  mov     [rbp+57h+var_98], 10h
0x180005a32  mov     [rbp+57h+var_90], 0
0x180005a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a3f  xor     eax, eax
0x180005a41  add     rsp, 0B8h
0x180005a48  pop     r14
0x180005a4a  pop     rdi
0x180005a4b  pop     rbx
0x180005a4c  pop     rbp
0x180005a4d  retn
```
