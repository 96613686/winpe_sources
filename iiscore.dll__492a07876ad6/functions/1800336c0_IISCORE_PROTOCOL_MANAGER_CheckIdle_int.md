# IISCORE_PROTOCOL_MANAGER::CheckIdle(int *)

- ea: `0x1800336c0`
- end: `0x18003372a`
- name: `?CheckIdle@IISCORE_PROTOCOL_MANAGER@@UEAAJPEAH@Z`
- size: `106`
- prototype: `__int64 __fastcall(IISCORE_PROTOCOL_MANAGER *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800336c0`

## import_xrefs

- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180033710`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180033710`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800336d4`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800336d4`
- `w3dt!UlAtqGetContextProperty` at `0x1800336f1`
- `w3dt!UlAtqGetContextProperty` at `0x1800336f1`

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
0x1800336c0  mov     [rsp+arg_0], rbx
0x1800336c5  push    rdi
0x1800336c6  sub     rsp, 20h
0x1800336ca  lea     rbx, [rcx+58h]
0x1800336ce  mov     rdi, rdx
0x1800336d1  mov     rcx, rbx
0x1800336d4  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800336db  nop     dword ptr [rax+rax+00h]
0x1800336e0  cmp     cs:?g_pW3Server@@3PEAVW3_SERVER@@EA, 0; W3_SERVER * g_pW3Server
0x1800336e8  jz      short loc_180033706
0x1800336ea  mov     edx, 3
0x1800336ef  xor     ecx, ecx
0x1800336f1  call    cs:__imp_?UlAtqGetContextProperty@@YAPEAXPEAXW4ULATQ_CONTEXT_PROPERTY_ID@@@Z; UlAtqGetContextProperty(void *,ULATQ_CONTEXT_PROPERTY_ID)
0x1800336f8  nop     dword ptr [rax+rax+00h]
0x1800336fd  xor     ecx, ecx
0x1800336ff  test    eax, eax
0x180033701  setz    cl
0x180033704  jmp     short loc_18003370B
0x180033706  mov     ecx, 1
0x18003370b  mov     [rdi], ecx
0x18003370d  mov     rcx, rbx
0x180033710  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180033717  nop     dword ptr [rax+rax+00h]
0x18003371c  mov     rbx, [rsp+28h+arg_0]
0x180033721  xor     eax, eax
0x180033723  add     rsp, 20h
0x180033727  pop     rdi
0x180033728  retn
```
