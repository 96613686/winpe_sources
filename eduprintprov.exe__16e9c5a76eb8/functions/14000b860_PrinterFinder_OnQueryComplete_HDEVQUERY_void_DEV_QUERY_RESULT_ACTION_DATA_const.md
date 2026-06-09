# PrinterFinder::_OnQueryComplete(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)

- ea: `0x14000b860`
- end: `0x14000b8a4`
- name: `?_OnQueryComplete@PrinterFinder@@CAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z`
- size: `68`
- prototype: `static void(struct HDEVQUERY__ *, void *, const struct _DEV_QUERY_RESULT_ACTION_DATA *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000b4a0`
- `0x14000b860`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000b898`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000b898`

## pseudocode

```c
void __fastcall PrinterFinder::_OnQueryComplete(
        struct HDEVQUERY__ *a1,
        PrinterFinder *a2,
        const struct _DEV_QUERY_RESULT_ACTION_DATA *a3)
{
  void *v4; // rcx

  if ( *(_DWORD *)a3 == 1 )
  {
    if ( !PrinterFinder::_OnDeviceUpdate(a2, (const struct _DEV_QUERY_RESULT_ACTION_DATA *)((char *)a3 + 8)) )
      return;
    v4 = *(void **)a2;
    goto LABEL_7;
  }
  if ( !*(_DWORD *)a3 && (unsigned int)(*((_DWORD *)a3 + 2) - 1) <= 1 )
  {
    v4 = *(void **)a2;
LABEL_7:
    SetEvent(v4);
  }
}

```

## disassembly

```asm
0x14000b860  push    rbx
0x14000b862  sub     rsp, 20h
0x14000b866  cmp     dword ptr [r8], 1
0x14000b86a  mov     rbx, rdx
0x14000b86d  jnz     short loc_14000B884
0x14000b86f  lea     rdx, [r8+8]; struct _DEV_OBJECT *
0x14000b873  mov     rcx, rbx; this
0x14000b876  call    ?_OnDeviceUpdate@PrinterFinder@@AEAA_NAEBU_DEV_OBJECT@@@Z; PrinterFinder::_OnDeviceUpdate(_DEV_OBJECT const &)
0x14000b87b  test    al, al
0x14000b87d  jz      short loc_14000B89E
0x14000b87f  mov     rcx, [rbx]
0x14000b882  jmp     short loc_14000B898
0x14000b884  cmp     dword ptr [r8], 0
0x14000b888  jnz     short loc_14000B89E
0x14000b88a  mov     eax, [r8+8]
0x14000b88e  dec     eax
0x14000b890  cmp     eax, 1
0x14000b893  ja      short loc_14000B89E
0x14000b895  mov     rcx, [rdx]; hEvent
0x14000b898  call    cs:__imp_SetEvent
0x14000b89e  add     rsp, 20h
0x14000b8a2  pop     rbx
0x14000b8a3  retn
```
