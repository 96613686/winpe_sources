# CAutoTearDown__lambda_bfc2a55aa93f2a22d8c708a7a0190810___::_CAutoTearDown__lambda_bfc2a55aa93f2a22d8c708a7a0190810___

- ea: `0x18002e7f0`
- end: `0x18002e818`
- name: `CAutoTearDown__lambda_bfc2a55aa93f2a22d8c708a7a0190810___::_CAutoTearDown__lambda_bfc2a55aa93f2a22d8c708a7a0190810___`
- size: `40`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18002e820`

## callees

- `0x18002e7f0`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x18002e80d`
- `ESENT!JetPrepareUpdate` at `0x18002e80d`

## pseudocode

```c
JET_ERR __fastcall CAutoTearDown__lambda_bfc2a55aa93f2a22d8c708a7a0190810___::_CAutoTearDown__lambda_bfc2a55aa93f2a22d8c708a7a0190810___(
        __int64 *a1)
{
  __int64 v1; // rcx
  JET_ERR result; // eax

  v1 = *a1;
  if ( v1 )
    return JetPrepareUpdate(*(_QWORD *)(*(_QWORD *)v1 + 8LL), *(_QWORD *)(*(_QWORD *)v1 + 24LL), 3u);
  return result;
}

```

## disassembly

```asm
0x18002e7f0  sub     rsp, 28h
0x18002e7f4  mov     rcx, [rcx]
0x18002e7f7  test    rcx, rcx
0x18002e7fa  jz      short loc_18002E813
0x18002e7fc  mov     rcx, [rcx]
0x18002e7ff  mov     r8d, 3; prep
0x18002e805  mov     rdx, [rcx+18h]; tableid
0x18002e809  mov     rcx, [rcx+8]; sesid
0x18002e80d  call    cs:__imp_JetPrepareUpdate
0x18002e813  add     rsp, 28h
0x18002e817  retn
```
