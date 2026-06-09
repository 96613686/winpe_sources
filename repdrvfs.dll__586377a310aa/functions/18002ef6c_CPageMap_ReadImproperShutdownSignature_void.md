# CPageMap::ReadImproperShutdownSignature(void *)

- ea: `0x18002ef6c`
- end: `0x18002f04c`
- name: `?ReadImproperShutdownSignature@CPageMap@@QEAAKPEAX@Z`
- size: `224`
- prototype: `unsigned int(CPageMap *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002e900`

## callees

- `0x1800012b8`
- `0x18002ef6c`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18002efb6`
- `wbemcomn!GetMemLogObject` at `0x18002eff4`
- `wbemcomn!GetMemLogObject` at `0x18002efb6`
- `wbemcomn!GetMemLogObject` at `0x18002eff4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002efc4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002f002`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002efc4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002f002`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002ef9e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002ef9e`

## pseudocode

```c
__int64 __fastcall CPageMap::ReadImproperShutdownSignature(CPageMap *this, void *a2)
{
  CMemoryLog *v2; // rax
  CVarObjHeap *v3; // rcx
  __int64 v4; // rdx
  CMemoryLog *MemLogObject; // rax
  DWORD v7; // [rsp+40h] [rbp+8h] BYREF
  int v8; // [rsp+44h] [rbp+Ch]
  int v9; // [rsp+50h] [rbp+18h] BYREF

  v8 = HIDWORD(this);
  v9 = 0;
  v7 = 0;
  if ( !ReadFile(a2, &v9, 4u, &v7, 0) || v7 != 4 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, 1358);
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 1358;
    }
    v4 = 10;
    goto LABEL_13;
  }
  if ( v9 )
    return 0;
  v2 = GetMemLogObject();
  CMemoryLog::Write(v2, 1358);
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v4 = 11;
LABEL_13:
    WPP_SF_d(*((_QWORD *)v3 + 2), v4, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 1358);
  }
  return 1358;
}

```

## disassembly

```asm
0x18002ef6c  mov     rax, rsp
0x18002ef6f  mov     [rax+8], rcx
0x18002ef73  sub     rsp, 38h
0x18002ef77  mov     rcx, rdx; hFile
0x18002ef7a  mov     dword ptr [rax+18h], 0
0x18002ef81  lea     rdx, [rax+18h]; lpBuffer
0x18002ef85  mov     dword ptr [rax+8], 0
0x18002ef8c  lea     r9, [rax+8]; lpNumberOfBytesRead
0x18002ef90  mov     qword ptr [rax-18h], 0
0x18002ef98  mov     r8d, 4; nNumberOfBytesToRead
0x18002ef9e  call    cs:__imp_ReadFile
0x18002efa4  test    eax, eax
0x18002efa6  jz      short loc_18002EFF4
0x18002efa8  cmp     [rsp+38h+arg_0], 4
0x18002efad  jnz     short loc_18002EFF4
0x18002efaf  cmp     [rsp+38h+arg_10], 0
0x18002efb4  jnz     short loc_18002EFF0
0x18002efb6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002efbc  mov     rcx, rax
0x18002efbf  mov     edx, 54Eh
0x18002efc4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002efca  mov     rcx, cs:WPP_GLOBAL_Control
0x18002efd1  lea     rax, WPP_GLOBAL_Control
0x18002efd8  cmp     rcx, rax
0x18002efdb  jz      short loc_18002F042
0x18002efdd  test    byte ptr [rcx+1Ch], 1
0x18002efe1  jz      short loc_18002F042
0x18002efe3  cmp     byte ptr [rcx+19h], 2
0x18002efe7  jb      short loc_18002F042
0x18002efe9  mov     edx, 0Bh
0x18002efee  jmp     short loc_18002F02C
0x18002eff0  xor     eax, eax
0x18002eff2  jmp     short loc_18002F047
0x18002eff4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002effa  mov     rcx, rax
0x18002effd  mov     edx, 54Eh
0x18002f002  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002f008  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f00f  lea     rax, WPP_GLOBAL_Control
0x18002f016  cmp     rcx, rax
0x18002f019  jz      short loc_18002F042
0x18002f01b  test    byte ptr [rcx+1Ch], 1
0x18002f01f  jz      short loc_18002F042
0x18002f021  cmp     byte ptr [rcx+19h], 2
0x18002f025  jb      short loc_18002F042
0x18002f027  mov     edx, 0Ah
0x18002f02c  mov     rcx, [rcx+10h]
0x18002f030  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18002f037  mov     r9d, 54Eh
0x18002f03d  call    WPP_SF_d
0x18002f042  mov     eax, 54Eh
0x18002f047  add     rsp, 38h
0x18002f04b  retn
```
