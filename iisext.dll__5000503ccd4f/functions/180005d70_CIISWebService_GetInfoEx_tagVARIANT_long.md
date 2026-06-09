# CIISWebService::GetInfoEx(tagVARIANT,long)

- ea: `0x180005d70`
- end: `0x180005da4`
- name: `?GetInfoEx@CIISWebService@@UEAAJUtagVARIANT@@J@Z`
- size: `52`
- prototype: `__int64 __fastcall(CIISWebService *__hidden this, struct tagVARIANT *__struct_ptr, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISWebService::GetInfoEx(CIISWebService *this, struct tagVARIANT *a2)
{
  __int64 v2; // rcx
  IRecordInfo *pRecInfo; // xmm1_8
  __int128 v5; // [rsp+20h] [rbp-28h] BYREF
  IRecordInfo *v6; // [rsp+30h] [rbp-18h]

  v2 = *((_QWORD *)this + 7);
  pRecInfo = a2->pRecInfo;
  v5 = *(_OWORD *)&a2->vt;
  v6 = pRecInfo;
  return (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v2 + 152LL))(v2, &v5);
}

```

## disassembly

```asm
0x180005d70  sub     rsp, 48h
0x180005d74  movups  xmm0, xmmword ptr [rdx]
0x180005d77  mov     rcx, [rcx+38h]
0x180005d7b  movsd   xmm1, qword ptr [rdx+10h]
0x180005d80  lea     rdx, [rsp+48h+var_28]
0x180005d85  movaps  [rsp+48h+var_28], xmm0
0x180005d8a  movsd   [rsp+48h+var_18], xmm1
0x180005d90  mov     rax, [rcx]
0x180005d93  mov     rax, [rax+98h]
0x180005d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d9f  add     rsp, 48h
0x180005da3  retn
```
