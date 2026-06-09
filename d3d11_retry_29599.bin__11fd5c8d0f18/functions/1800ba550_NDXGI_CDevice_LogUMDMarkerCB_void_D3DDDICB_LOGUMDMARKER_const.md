# NDXGI::CDevice::LogUMDMarkerCB(void *,D3DDDICB_LOGUMDMARKER const *)

- ea: `0x1800ba550`
- end: `0x1800ba6b9`
- name: `?LogUMDMarkerCB@CDevice@NDXGI@@KAJPEAXPEBUD3DDDICB_LOGUMDMARKER@@@Z`
- size: `361`
- prototype: `__int64 __fastcall(void *, const struct D3DDDICB_LOGUMDMARKER *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180078890`
- `0x1800a9d20`
- `0x1800ba550`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800ba645`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800ba645`
- `ntdll!EtwEventWrite` at `0x1800ba690`
- `ntdll!EtwEventWrite` at `0x1800ba690`

## pseudocode

```c
__int64 __fastcall NDXGI::CDevice::LogUMDMarkerCB(_QWORD *a1, const struct D3DDDICB_LOGUMDMARKER *a2)
{
  __int64 v4; // rax
  int v5; // ecx
  const wchar_t *v6; // rcx
  int v7; // ecx
  bool v8; // zf
  void *v9; // rax
  int v11; // [rsp+20h] [rbp-49h] BYREF
  __int64 v12; // [rsp+28h] [rbp-41h] BYREF
  _BYTE v13[32]; // [rsp+30h] [rbp-39h] BYREF
  _QWORD v14[11]; // [rsp+50h] [rbp-19h] BYREF
  int v15; // [rsp+A8h] [rbp+3Fh]
  int v16; // [rsp+ACh] [rbp+43h]

  if ( dword_1802282A4
    && (qword_180228290 & 0x8000000000000400uLL) != 0
    && (qword_180228298 & 0x8000000000000400uLL) == qword_180228298
    && (*(_BYTE *)(NDXGI::CDevice::GetCaps(a1 + 2, v13) + 8) & 0x40) != 0 )
  {
    v14[1] = 8;
    v14[0] = (char *)a2 + 8;
    v12 = *(_QWORD *)(*(_QWORD *)(a1[9] + 1080LL) + 168LL);
    v14[2] = &v12;
    v4 = *(_QWORD *)a2;
    v14[3] = 8;
    v5 = *(_DWORD *)(v4 + 8);
    v14[4] = &v11;
    v11 = v5;
    v6 = (const wchar_t *)*((_QWORD *)a2 + 3);
    v14[6] = (char *)a2 + 16;
    v14[8] = (char *)a2 + 20;
    v14[5] = 4;
    v14[7] = 4;
    v14[9] = 4;
    if ( v6 )
      v7 = 2 * wcslen(v6) + 2;
    else
      v7 = 2;
    v8 = *((_QWORD *)a2 + 3) == 0;
    v9 = &unk_1801F94F0;
    v15 = v7;
    if ( !v8 )
      v9 = (void *)*((_QWORD *)a2 + 3);
    v14[10] = v9;
    v16 = 0;
    EtwEventWrite(Direct3D11EtwProviderGuid_Context, &EventD3D11CustomDriverMarker, 6, v14);
  }
  return 0;
}

```

## disassembly

```asm
0x1800ba550  mov     [rsp-8+arg_0], rbx
0x1800ba555  mov     [rsp-8+arg_10], rdi
0x1800ba55a  push    rbp
0x1800ba55b  lea     rbp, [rsp-57h]
0x1800ba560  sub     rsp, 0C0h
0x1800ba567  mov     rax, cs:__security_cookie
0x1800ba56e  xor     rax, rsp
0x1800ba571  mov     [rbp+57h+var_10], rax
0x1800ba575  cmp     cs:dword_1802282A4, 0
0x1800ba57c  mov     rbx, rdx
0x1800ba57f  mov     rdi, rcx
0x1800ba582  jz      loc_1800BA696
0x1800ba588  mov     rdx, 8000000000000400h
0x1800ba592  test    cs:qword_180228290, rdx
0x1800ba599  jz      loc_1800BA696
0x1800ba59f  mov     rax, cs:qword_180228298
0x1800ba5a6  and     rax, rdx
0x1800ba5a9  cmp     rax, cs:qword_180228298
0x1800ba5b0  jnz     loc_1800BA696
0x1800ba5b6  add     rcx, 10h
0x1800ba5ba  lea     rdx, [rbp+57h+var_90]
0x1800ba5be  call    ?GetCaps@CDevice@NDXGI@@UEAA?AUDXGI_INTERNAL_DEVICE_CAPS@@XZ; NDXGI::CDevice::GetCaps(void)
0x1800ba5c3  test    byte ptr [rax+8], 40h
0x1800ba5c7  jz      loc_1800BA696
0x1800ba5cd  mov     [rbp+57h+var_68], 8
0x1800ba5d5  lea     rax, [rbx+8]
0x1800ba5d9  mov     [rbp+57h+var_70], rax
0x1800ba5dd  mov     rax, [rdi+48h]
0x1800ba5e1  mov     rcx, [rax+438h]
0x1800ba5e8  mov     rax, [rcx+0A8h]
0x1800ba5ef  mov     [rbp+57h+var_98], rax
0x1800ba5f3  lea     rax, [rbp+57h+var_98]
0x1800ba5f7  mov     [rbp+57h+var_60], rax
0x1800ba5fb  mov     rax, [rbx]
0x1800ba5fe  mov     [rbp+57h+var_58], 8
0x1800ba606  mov     ecx, [rax+8]
0x1800ba609  lea     rax, [rbp+57h+var_A0]
0x1800ba60d  mov     [rbp+57h+var_50], rax
0x1800ba611  lea     rax, [rbx+10h]
0x1800ba615  mov     [rbp+57h+var_A0], ecx
0x1800ba618  mov     rcx, [rbx+18h]; String
0x1800ba61c  mov     [rbp+57h+var_40], rax
0x1800ba620  lea     rax, [rbx+14h]
0x1800ba624  mov     [rbp+57h+var_30], rax
0x1800ba628  mov     [rbp+57h+var_48], 4
0x1800ba630  mov     [rbp+57h+var_38], 4
0x1800ba638  mov     [rbp+57h+var_28], 4
0x1800ba640  test    rcx, rcx
0x1800ba643  jz      short loc_1800BA654
0x1800ba645  call    cs:__imp_wcslen
0x1800ba64b  lea     ecx, ds:2[rax*2]
0x1800ba652  jmp     short loc_1800BA659
0x1800ba654  mov     ecx, 2
0x1800ba659  cmp     qword ptr [rbx+18h], 0
0x1800ba65e  lea     rax, unk_1801F94F0
0x1800ba665  mov     [rbp+57h+var_18], ecx
0x1800ba668  lea     r9, [rbp+57h+var_70]
0x1800ba66c  cmovnz  rax, [rbx+18h]
0x1800ba671  lea     rdx, EventD3D11CustomDriverMarker
0x1800ba678  mov     rcx, cs:Direct3D11EtwProviderGuid_Context
0x1800ba67f  mov     r8d, 6
0x1800ba685  mov     [rbp+57h+var_20], rax
0x1800ba689  mov     [rbp+57h+var_14], 0
0x1800ba690  call    cs:__imp_EtwEventWrite
0x1800ba696  xor     eax, eax
0x1800ba698  mov     rcx, [rbp+57h+var_10]
0x1800ba69c  xor     rcx, rsp; StackCookie
0x1800ba69f  call    __security_check_cookie
0x1800ba6a4  lea     r11, [rsp+0C0h+var_s0]
0x1800ba6ac  mov     rbx, [r11+10h]
0x1800ba6b0  mov     rdi, [r11+20h]
0x1800ba6b4  mov     rsp, r11
0x1800ba6b7  pop     rbp
0x1800ba6b8  retn
```
