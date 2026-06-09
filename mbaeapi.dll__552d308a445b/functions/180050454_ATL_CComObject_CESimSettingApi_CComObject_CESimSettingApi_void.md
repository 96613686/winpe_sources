# ATL::CComObject<CESimSettingApi>::CComObject<CESimSettingApi>(void *)

- ea: `0x180050454`
- end: `0x180050555`
- name: `??0?$CComObject@VCESimSettingApi@@@ATL@@QEAA@PEAX@Z`
- size: `257`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180051d9c`

## callees

- `0x1800028ec`
- `0x180002efc`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180050505`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005051d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180050505`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005051d`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CESimSettingApi>::CComObject<CESimSettingApi>(__int64 a1)
{
  _QWORD *v2; // rbx
  _QWORD *v3; // rax

  *(_DWORD *)(a1 + 8) = 0;
  *(_OWORD *)(a1 + 16) = 0;
  *(_OWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_BYTE *)(a1 + 56) = 0;
  *(_QWORD *)a1 = &CESimSettingApi::`vftable';
  *(GUID *)(a1 + 132) = GUID_NULL;
  *(_QWORD *)(a1 + 152) = 0;
  *(_DWORD *)(a1 + 180) = -1;
  *(_QWORD *)(a1 + 184) = 0;
  v2 = (_QWORD *)(a1 + 192);
  *(_QWORD *)(a1 + 192) = 0;
  *(_QWORD *)(a1 + 200) = 0;
  v3 = operator new(0x28u);
  *v3 = v3;
  v3[1] = v3;
  v3[2] = v3;
  *((_WORD *)v3 + 12) = 257;
  *v2 = v3;
  *(_DWORD *)(a1 + 216) = 0;
  memset_0((void *)(a1 + 64), 0, 0x42u);
  *(_QWORD *)(a1 + 160) = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 168) = CreateEventW(0, 0, 1, 0);
  *(_QWORD *)a1 = &ATL::CComObject<CESimSettingApi>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  return a1;
}

```

## disassembly

```asm
0x180050454  mov     [rsp+arg_10], rbx
0x180050459  mov     [rsp+arg_0], rcx
0x18005045e  push    rdi
0x18005045f  sub     rsp, 20h
0x180050463  mov     rdi, rcx
0x180050466  mov     dword ptr [rcx+8], 0
0x18005046d  xorps   xmm0, xmm0
0x180050470  xor     eax, eax
0x180050472  movups  xmmword ptr [rcx+10h], xmm0
0x180050476  movups  xmmword ptr [rcx+20h], xmm0
0x18005047a  mov     [rcx+30h], rax
0x18005047e  mov     [rcx+38h], al
0x180050481  lea     rax, ??_7CESimSettingApi@@6B@; const CESimSettingApi::`vftable'
0x180050488  mov     [rcx], rax
0x18005048b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180050492  movdqu  xmmword ptr [rcx+84h], xmm0
0x18005049a  mov     qword ptr [rcx+98h], 0
0x1800504a5  mov     dword ptr [rcx+0B4h], 0FFFFFFFFh
0x1800504af  xor     eax, eax
0x1800504b1  mov     [rcx+0B8h], rax
0x1800504b8  lea     rbx, [rcx+0C0h]
0x1800504bf  mov     [rbx], rax
0x1800504c2  mov     [rbx+8], rax
0x1800504c6  lea     ecx, [rax+28h]; Size
0x1800504c9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800504ce  mov     [rax], rax
0x1800504d1  mov     [rax+8], rax
0x1800504d5  mov     [rax+10h], rax
0x1800504d9  mov     word ptr [rax+18h], 101h
0x1800504df  mov     [rbx], rax
0x1800504e2  mov     dword ptr [rdi+0D8h], 0
0x1800504ec  lea     rcx, [rdi+40h]; void *
0x1800504f0  xor     edx, edx; Val
0x1800504f2  lea     r8d, [rdx+42h]; Size
0x1800504f6  call    memset_0
0x1800504fb  xor     r9d, r9d; lpName
0x1800504fe  xor     r8d, r8d; bInitialState
0x180050501  xor     edx, edx; bManualReset
0x180050503  xor     ecx, ecx; lpEventAttributes
0x180050505  call    cs:__imp_CreateEventW
0x18005050b  mov     [rdi+0A0h], rax
0x180050512  xor     r9d, r9d; lpName
0x180050515  xor     edx, edx; bManualReset
0x180050517  xor     ecx, ecx; lpEventAttributes
0x180050519  lea     r8d, [r9+1]; bInitialState
0x18005051d  call    cs:__imp_CreateEventW
0x180050523  mov     [rdi+0A8h], rax
0x18005052a  lea     rax, ??_7?$CComObject@VCESimSettingApi@@@ATL@@6B@; const ATL::CComObject<CESimSettingApi>::`vftable'
0x180050531  mov     [rdi], rax
0x180050534  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18005053b  mov     rax, [rcx]
0x18005053e  mov     rax, [rax+8]
0x180050542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050547  mov     rax, rdi
0x18005054a  mov     rbx, [rsp+28h+arg_10]
0x18005054f  add     rsp, 20h
0x180050553  pop     rdi
0x180050554  retn
```
