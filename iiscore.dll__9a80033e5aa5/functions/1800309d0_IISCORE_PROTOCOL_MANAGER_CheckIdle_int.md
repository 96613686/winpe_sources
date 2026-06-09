# IISCORE_PROTOCOL_MANAGER::CheckIdle(int *)

- ea: `0x1800309d0`
- end: `0x180030a27`
- name: `?CheckIdle@IISCORE_PROTOCOL_MANAGER@@UEAAJPEAH@Z`
- size: `87`
- prototype: `__int64 __fastcall(IISCORE_PROTOCOL_MANAGER *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800309d0`

## import_xrefs

- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180030a14`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180030a14`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800309e4`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800309e4`
- `w3dt!UlAtqGetContextProperty` at `0x1800309fb`
- `w3dt!UlAtqGetContextProperty` at `0x1800309fb`

## pseudocode

```c
__int64 __fastcall IISCORE_PROTOCOL_MANAGER::CheckIdle(IISCORE_PROTOCOL_MANAGER *this, int *a2)
{
  CReaderWriterLock3 *v2; // rbx
  BOOL v4; // ecx

  v2 = (IISCORE_PROTOCOL_MANAGER *)((char *)this + 88);
  CReaderWriterLock3::ReadLock((IISCORE_PROTOCOL_MANAGER *)((char *)this + 88));
  if ( g_pW3Server )
    v4 = UlAtqGetContextProperty(0, 3) == 0;
  else
    v4 = 1;
  *a2 = v4;
  CReaderWriterLock3::ReadUnlock(v2);
  return 0;
}

```

## disassembly

```asm
0x1800309d0  mov     [rsp+arg_0], rbx
0x1800309d5  push    rdi
0x1800309d6  sub     rsp, 20h
0x1800309da  lea     rbx, [rcx+58h]
0x1800309de  mov     rdi, rdx
0x1800309e1  mov     rcx, rbx
0x1800309e4  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800309ea  cmp     cs:?g_pW3Server@@3PEAVW3_SERVER@@EA, 0; W3_SERVER * g_pW3Server
0x1800309f2  jz      short loc_180030A0A
0x1800309f4  mov     edx, 3
0x1800309f9  xor     ecx, ecx
0x1800309fb  call    cs:__imp_?UlAtqGetContextProperty@@YAPEAXPEAXW4ULATQ_CONTEXT_PROPERTY_ID@@@Z; UlAtqGetContextProperty(void *,ULATQ_CONTEXT_PROPERTY_ID)
0x180030a01  xor     ecx, ecx
0x180030a03  test    eax, eax
0x180030a05  setz    cl
0x180030a08  jmp     short loc_180030A0F
0x180030a0a  mov     ecx, 1
0x180030a0f  mov     [rdi], ecx
0x180030a11  mov     rcx, rbx
0x180030a14  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180030a1a  mov     rbx, [rsp+28h+arg_0]
0x180030a1f  xor     eax, eax
0x180030a21  add     rsp, 20h
0x180030a25  pop     rdi
0x180030a26  retn
```
