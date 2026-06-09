# CMsftDiscMaster2::FinalRelease(void)

- ea: `0x180001194`
- end: `0x180001202`
- name: `?FinalRelease@CMsftDiscMaster2@@QEAAXXZ`
- size: `110`
- prototype: `void __fastcall(CMsftDiscMaster2 *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ef6c`
- `0x180027f80`

## callees

- `0x180001194`
- `0x1800017cc`
- `0x180001804`
- `0x180028ad8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800011fb`

## pseudocode

```c
void __fastcall CMsftDiscMaster2::FinalRelease(CMsftDiscMaster2 *this)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, WPP_3a90062079c236e25d7a2c183328c269_Traceguids, this);
  }
  CMsftDiscMaster2::Self = 0;
  CMsftDiscMaster2::UnregisterDeviceInterfaceNotification(this);
  CMsftDiscMaster2::FreeCachedDeviceStrings(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
}

```

## disassembly

```asm
0x180001194  push    rbx
0x180001196  sub     rsp, 20h
0x18000119a  mov     rbx, rcx
0x18000119d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800011a4  lea     rax, WPP_GLOBAL_Control
0x1800011ab  cmp     rcx, rax
0x1800011ae  jz      short loc_1800011D4
0x1800011b0  test    byte ptr [rcx+6Ch], 2
0x1800011b4  jz      short loc_1800011D4
0x1800011b6  cmp     byte ptr [rcx+69h], 4
0x1800011ba  jb      short loc_1800011D4
0x1800011bc  mov     rcx, [rcx+60h]
0x1800011c0  lea     r8, WPP_3a90062079c236e25d7a2c183328c269_Traceguids
0x1800011c7  mov     edx, 0Ah
0x1800011cc  mov     r9, rbx
0x1800011cf  call    WPP_SF_q
0x1800011d4  mov     rcx, rbx; this
0x1800011d7  mov     cs:?Self@CMsftDiscMaster2@@2PEAV1@EA, 0; CMsftDiscMaster2 * CMsftDiscMaster2::Self
0x1800011e2  call    ?UnregisterDeviceInterfaceNotification@CMsftDiscMaster2@@QEAAXXZ; CMsftDiscMaster2::UnregisterDeviceInterfaceNotification(void)
0x1800011e7  mov     rcx, rbx; this
0x1800011ea  call    ?FreeCachedDeviceStrings@CMsftDiscMaster2@@AEAAXXZ; CMsftDiscMaster2::FreeCachedDeviceStrings(void)
0x1800011ef  lea     rcx, [rbx+88h]
0x1800011f6  add     rsp, 20h
0x1800011fa  pop     rbx
0x1800011fb  jmp     cs:__imp_DeleteCriticalSection
```
