# CJob::GetClassID(_GUID *)

- ea: `0x18000d630`
- end: `0x18000d63e`
- name: `?GetClassID@CJob@@UEAAJPEAU_GUID@@@Z`
- size: `14`
- prototype: `__int64 __fastcall(CJob *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, service_task, broker_com_uri`

## pseudocode

```c
__int64 __fastcall CJob::GetClassID(CJob *this, struct _GUID *a2)
{
  __int64 result; // rax

  result = 0;
  *a2 = CLSID_CTask;
  return result;
}

```

## disassembly

```asm
0x18000d630  movups  xmm0, xmmword ptr cs:CLSID_CTask.Data1
0x18000d637  xor     eax, eax
0x18000d639  movdqu  xmmword ptr [rdx], xmm0
0x18000d63d  retn
```
