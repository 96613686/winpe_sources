# IsOffline

- ea: `0x1400198b0`
- end: `0x14001996d`
- name: `IsOffline`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140014fc0`

## callees

- `0x140003280`
- `0x1400198b0`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14001992c`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14001992c`

## string_xrefs

- `0x1400198e9`: `\Registry\Machine\System\MountedDevices\Offline`

## pseudocode

```c
bool __fastcall IsOffline(__int64 a1)
{
  _QWORD v3[15]; // [rsp+30h] [rbp-78h] BYREF
  int v4; // [rsp+B0h] [rbp+8h] BYREF
  int v5; // [rsp+B8h] [rbp+10h] BYREF

  v4 = 0;
  v5 = 0;
  memset(v3, 0, 0x70u);
  v3[2] = *(_QWORD *)(a1 + 8);
  LODWORD(v3[1]) = 288;
  v3[3] = &v4;
  LODWORD(v3[4]) = 67108868;
  v3[5] = &v5;
  LODWORD(v3[6]) = 4;
  return (int)RtlQueryRegistryValuesEx(0, L"\\Registry\\Machine\\System\\MountedDevices\\Offline", v3, 0, 0) >= 0 && v4;
}

```

## disassembly

```asm
0x1400198b0  mov     rax, rsp
0x1400198b3  mov     [rax+18h], rbx
0x1400198b7  push    rdi
0x1400198b8  sub     rsp, 0A0h
0x1400198bf  mov     rbx, rcx
0x1400198c2  xor     edi, edi
0x1400198c4  lea     rcx, [rax-78h]; void *
0x1400198c8  mov     [rax+8], edi
0x1400198cb  xor     edx, edx; Val
0x1400198cd  mov     [rax+10h], edi
0x1400198d0  mov     r8d, 70h ; 'p'; Size
0x1400198d6  call    memset
0x1400198db  mov     rax, [rbx+8]
0x1400198df  lea     r8, [rsp+0A8h+var_78]
0x1400198e4  mov     [rsp+0A8h+var_68], rax
0x1400198e9  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\MountedDev"...
0x1400198f0  lea     rax, [rsp+0A8h+arg_0]
0x1400198f8  mov     [rsp+0A8h+var_70], 120h
0x140019900  mov     [rsp+0A8h+var_60], rax
0x140019905  xor     r9d, r9d
0x140019908  lea     rax, [rsp+0A8h+arg_8]
0x140019910  mov     [rsp+0A8h+var_58], 4000004h
0x140019918  xor     ecx, ecx
0x14001991a  mov     [rsp+0A8h+var_50], rax
0x14001991f  mov     [rsp+0A8h+var_48], 4
0x140019927  mov     [rsp+0A8h+var_88], rdi
0x14001992c  call    cs:__imp_RtlQueryRegistryValuesEx
0x140019933  nop     dword ptr [rax+rax+00h]
0x140019938  test    eax, eax
0x14001993a  js      short loc_140019959
0x14001993c  cmp     [rsp+0A8h+arg_0], edi
0x140019943  jz      short loc_140019959
0x140019945  mov     al, 1
0x140019947  mov     rbx, [rsp+0A8h+arg_10]
0x14001994f  add     rsp, 0A0h
0x140019956  pop     rdi
0x140019957  retn
0x140019959  mov     rbx, [rsp+0A8h+arg_10]
0x140019961  xor     al, al
0x140019963  add     rsp, 0A0h
0x14001996a  pop     rdi
0x14001996b  retn
```
