# CDirectMusicUMAPort::InstantiatePin(ulong,void * *)

- ea: `0x18001fdd8`
- end: `0x18001fea4`
- name: `?InstantiatePin@CDirectMusicUMAPort@@AEAAJKPEAPEAX@Z`
- size: `204`
- prototype: `__int64 __fastcall(CDirectMusicUMAPort *__hidden this, unsigned int, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001f51c`

## callees

- `0x18001fdd8`

## import_xrefs

- `ksuser!KsCreatePin` at `0x18001fe76`
- `ksuser!KsCreatePin` at `0x18001fe76`

## pseudocode

```c
signed int __fastcall CDirectMusicUMAPort::InstantiatePin(CDirectMusicUMAPort *this, ULONG a2, void **a3)
{
  void *v3; // rcx
  signed int result; // eax
  bool v6; // sf
  $58C2C1BF6568EE28BD9B872E6BA03976 Connect; // [rsp+20h] [rbp-39h] BYREF
  int v8; // [rsp+68h] [rbp+Fh]
  __int64 v9; // [rsp+6Ch] [rbp+13h]
  int v10; // [rsp+74h] [rbp+1Bh]
  GUID v11; // [rsp+78h] [rbp+1Fh]
  GUID v12; // [rsp+88h] [rbp+2Fh]
  GUID v13; // [rsp+98h] [rbp+3Fh]
  HANDLE ConnectionHandle; // [rsp+C0h] [rbp+67h] BYREF

  v3 = (void *)*((_QWORD *)this + 164);
  Connect.PinId = a2;
  Connect.Interface.Set = GUID_1a8766a0_62ce_11cf_a5d6_28db04c10000;
  ConnectionHandle = 0;
  *(&Connect.PinId + 1) = 0;
  Connect.Medium.Set = GUID_4747b320_62ce_11cf_a5d6_28db04c10000;
  v9 = 0;
  v10 = 0;
  *(&Connect.Interface.Alignment + 2) = 0;
  v11 = GUID_e725d360_62cc_11cf_a5d6_28db04c10000;
  *(&Connect.Medium.Alignment + 2) = 0;
  Connect.PinToHandle = 0;
  Connect.Priority.PriorityClass = 0x40000000;
  v13 = GUID_0f6417d6_c318_11d0_a43f_00a0c9223196;
  Connect.Priority.PrioritySubClass = 1;
  v8 = 64;
  v12 = GUID_1a82f8bc_3f8b_11d2_b774_0060083316c1;
  result = KsCreatePin(v3, &Connect, 0xC0000000, &ConnectionHandle);
  v6 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v6 = result < 0;
  }
  if ( !v6 )
    *a3 = ConnectionHandle;
  return result;
}

```

## disassembly

```asm
0x18001fdd8  mov     [rsp-8+arg_8], rbx
0x18001fddd  push    rbp
0x18001fdde  lea     rbp, [rsp-57h]
0x18001fde3  sub     rsp, 0B0h
0x18001fdea  movups  xmm0, xmmword ptr cs:_GUID_1a8766a0_62ce_11cf_a5d6_28db04c10000.Data1
0x18001fdf1  mov     rcx, [rcx+520h]; FilterHandle
0x18001fdf8  xor     eax, eax
0x18001fdfa  movups  xmm1, xmmword ptr cs:_GUID_1a82f8bc_3f8b_11d2_b774_0060083316c1.Data1
0x18001fe01  mov     rbx, r8
0x18001fe04  mov     [rbp+57h+Connect.PinId], edx
0x18001fe07  movdqu  xmmword ptr [rbp+57h+Connect.Interface], xmm0
0x18001fe0c  lea     r9, [rbp+57h+ConnectionHandle]; ConnectionHandle
0x18001fe10  mov     r8d, 0C0000000h; DesiredAccess
0x18001fe16  movups  xmm0, xmmword ptr cs:_GUID_4747b320_62ce_11cf_a5d6_28db04c10000.Data1
0x18001fe1d  lea     rdx, [rbp+57h+Connect]; Connect
0x18001fe21  mov     [rbp+57h+ConnectionHandle], 0
0x18001fe29  mov     dword ptr [rbp+57h+Connect+34h], eax
0x18001fe2c  movdqu  xmmword ptr [rbp+57h+Connect.Medium], xmm0
0x18001fe31  mov     [rbp+57h+var_44], rax
0x18001fe35  movups  xmm0, xmmword ptr cs:_GUID_e725d360_62cc_11cf_a5d6_28db04c10000.Data1
0x18001fe3c  mov     [rbp+57h+var_3C], eax
0x18001fe3f  mov     qword ptr [rbp+57h+Connect.Interface+10h], rax
0x18001fe43  movdqu  [rbp+57h+var_38], xmm0
0x18001fe48  mov     qword ptr [rbp+57h+Connect.Medium+10h], rax
0x18001fe4c  movups  xmm0, xmmword ptr cs:_GUID_0f6417d6_c318_11d0_a43f_00a0c9223196.Data1
0x18001fe53  mov     [rbp+57h+Connect.PinToHandle], rax
0x18001fe57  mov     [rbp+57h+Connect.Priority.PriorityClass], 40000000h
0x18001fe5e  movdqu  [rbp+57h+var_18], xmm0
0x18001fe63  mov     [rbp+57h+Connect.Priority.PrioritySubClass], 1
0x18001fe6a  mov     [rbp+57h+var_48], 40h ; '@'
0x18001fe71  movdqu  [rbp+57h+var_28], xmm1
0x18001fe76  call    cs:__imp_KsCreatePin
0x18001fe7c  test    eax, eax
0x18001fe7e  jle     short loc_18001FE8A
0x18001fe80  movzx   eax, ax
0x18001fe83  or      eax, 80070000h
0x18001fe88  test    eax, eax
0x18001fe8a  js      short loc_18001FE93
0x18001fe8c  mov     rcx, [rbp+57h+ConnectionHandle]
0x18001fe90  mov     [rbx], rcx
0x18001fe93  mov     rbx, [rsp+0B0h+arg_8]
0x18001fe9b  add     rsp, 0B0h
0x18001fea2  pop     rbp
0x18001fea3  retn
```
