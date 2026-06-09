# CRdpWindowTracker::DeleteWindowNode(RDP_TRACKED_WINDOW_NODE *)

- ea: `0x14005c278`
- end: `0x14005c2ab`
- name: `?DeleteWindowNode@CRdpWindowTracker@@AEAAXPEAURDP_TRACKED_WINDOW_NODE@@@Z`
- size: `51`
- prototype: `void(CRdpWindowTracker *__hidden this, struct RDP_TRACKED_WINDOW_NODE *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x14005c038`
- `0x14005f1c0`

## callees

- `0x14005c278`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005c29f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005c29f`
- `GDI32!DeleteObject` at `0x14005c28e`
- `GDI32!DeleteObject` at `0x14005c28e`

## pseudocode

```c
void __fastcall CRdpWindowTracker::DeleteWindowNode(CRdpWindowTracker *this, struct RDP_TRACKED_WINDOW_NODE *a2)
{
  void *v2; // rcx

  if ( a2 )
  {
    v2 = (void *)*((_QWORD *)a2 + 12);
    if ( v2 )
    {
      DeleteObject(v2);
      *((_QWORD *)a2 + 12) = 0;
    }
    CoTaskMemFree(a2);
  }
}

```

## disassembly

```asm
0x14005c278  test    rdx, rdx
0x14005c27b  jz      short locret_14005C2AA
0x14005c27d  push    rbx
0x14005c27e  sub     rsp, 20h
0x14005c282  mov     rcx, [rdx+60h]; ho
0x14005c286  mov     rbx, rdx
0x14005c289  test    rcx, rcx
0x14005c28c  jz      short loc_14005C29C
0x14005c28e  call    cs:__imp_DeleteObject
0x14005c294  mov     qword ptr [rbx+60h], 0
0x14005c29c  mov     rcx, rbx; pv
0x14005c29f  call    cs:__imp_CoTaskMemFree
0x14005c2a5  add     rsp, 20h
0x14005c2a9  pop     rbx
0x14005c2aa  retn
```
