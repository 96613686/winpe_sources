# ConstructReconnectPacket(_CNOTIFY_PACKET * *,wchar_t const *,_CNOTIFY_EVENT *)

- ea: `0x18005bef0`
- end: `0x18005c10b`
- name: `?ConstructReconnectPacket@@YAKPEAPEAU_CNOTIFY_PACKET@@PEB_WPEAU_CNOTIFY_EVENT@@@Z`
- size: `539`
- prototype: `unsigned int(struct _CNOTIFY_PACKET **, const wchar_t *, struct _CNOTIFY_EVENT *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18005b1b4`
- `0x180060a54`

## callees

- `0x18001236c`
- `0x180025478`
- `0x18005bef0`
- `0x18005c960`
- `0x18005cea0`
- `0x18006f910`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c0e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c0e6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005bf26`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005c053`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005bf26`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005c053`

## string_xrefs

- `0x18005bfe8`: `Failed to create CLUSTER_CHANGE_CLUSTER_RECONNECT notification - %d`
- `0x18005c0c2`: `Failed to copy name for CLUSTER_CHANGE_CLUSTER_RECONNECT notification - %d`

## pseudocode

```c

```
