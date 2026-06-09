# GetDeviceProperty(void *,_DO_DEVINFO_DATA *,ulong)

- ea: `0x180021500`
- end: `0x1800215b2`
- name: `?GetDeviceProperty@@YAPEAEPEAXPEAU_DO_DEVINFO_DATA@@K@Z`
- size: `178`
- prototype: `unsigned __int8 *__fastcall(void *, struct _DO_DEVINFO_DATA *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800213b8`

## callees

- `0x180021500`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021558`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021558`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800215a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800215a8`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x180021540`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x180021588`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x180021540`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x180021588`

## pseudocode

```c
unsigned __int8 *__fastcall GetDeviceProperty(void *a1, struct _DO_DEVINFO_DATA *a2)
{
  HLOCAL v4; // rax
  void *v5; // rbx
  unsigned int v7; // [rsp+60h] [rbp+18h] BYREF

  v7 = 0;
  DevObjGetDeviceRegistryProperty(a1, a2, 0, 0, 0, 0, &v7);
  v7 += 2;
  v4 = LocalAlloc(0x40u, v7);
  v5 = v4;
  if ( v4 && !(unsigned int)DevObjGetDeviceRegistryProperty(a1, a2, 0, 0, v4, v7, 0) )
  {
    LocalFree(v5);
    return 0;
  }
  return (unsigned __int8 *)v5;
}

```

## disassembly

```asm
0x180021500  mov     r11, rsp
0x180021503  mov     [r11+8], rbx
0x180021507  mov     [r11+10h], rsi
0x18002150b  mov     [r11+18h], r8d
0x18002150f  push    rdi
0x180021510  sub     rsp, 40h
0x180021514  lea     rax, [r11+18h]
0x180021518  mov     [rsp+48h+arg_10], 0
0x180021520  mov     [r11-18h], rax
0x180021524  xor     r9d, r9d
0x180021527  mov     [rsp+48h+var_20], 0
0x18002152f  xor     r8d, r8d
0x180021532  mov     qword ptr [r11-28h], 0
0x18002153a  mov     rdi, rdx
0x18002153d  mov     rsi, rcx
0x180021540  call    cs:__imp_DevObjGetDeviceRegistryProperty
0x180021546  mov     eax, [rsp+48h+arg_10]
0x18002154a  mov     ecx, 40h ; '@'; uFlags
0x18002154f  add     eax, 2
0x180021552  mov     edx, eax; uBytes
0x180021554  mov     [rsp+48h+arg_10], eax
0x180021558  call    cs:__imp_LocalAlloc
0x18002155e  mov     rbx, rax
0x180021561  test    rax, rax
0x180021564  jz      short loc_180021592
0x180021566  mov     ecx, [rsp+48h+arg_10]
0x18002156a  xor     r9d, r9d
0x18002156d  mov     [rsp+48h+var_18], 0
0x180021576  xor     r8d, r8d
0x180021579  mov     [rsp+48h+var_20], ecx
0x18002157d  mov     rdx, rdi
0x180021580  mov     rcx, rsi
0x180021583  mov     [rsp+48h+var_28], rax
0x180021588  call    cs:__imp_DevObjGetDeviceRegistryProperty
0x18002158e  test    eax, eax
0x180021590  jz      short loc_1800215A5
0x180021592  mov     rsi, [rsp+48h+arg_8]
0x180021597  mov     rax, rbx
0x18002159a  mov     rbx, [rsp+48h+arg_0]
0x18002159f  add     rsp, 40h
0x1800215a3  pop     rdi
0x1800215a4  retn
0x1800215a5  mov     rcx, rbx; hMem
0x1800215a8  call    cs:__imp_LocalFree
0x1800215ae  xor     ebx, ebx
0x1800215b0  jmp     short loc_180021592
```
