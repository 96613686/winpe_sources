# ObjectHandle::Clear(void)

- ea: `0x18000d1dc`
- end: `0x18000d20e`
- name: `?Clear@ObjectHandle@@QEAAXXZ`
- size: `50`
- prototype: `void __fastcall(ObjectHandle *__hidden this)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x1800031a0`
- `0x1800059c4`
- `0x180006100`
- `0x18000b6ac`
- `0x18000b7a4`
- `0x18000b8bc`
- `0x18000c280`
- `0x18000c500`
- `0x18000cae8`
- `0x18000d1ac`

## callees

- `0x18000d1dc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d1f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d1f3`

## pseudocode

```c
void __fastcall ObjectHandle::Clear(ObjectHandle *this)
{
  char *v2; // rcx

  v2 = (char *)*((_QWORD *)this + 1);
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v2);
  *((_QWORD *)this + 1) = 0;
}

```

## disassembly

```asm
0x18000d1dc  push    rbx
0x18000d1de  sub     rsp, 20h
0x18000d1e2  mov     rbx, rcx
0x18000d1e5  mov     rcx, [rcx+8]; hObject
0x18000d1e9  lea     rax, [rcx-1]
0x18000d1ed  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d1f1  ja      short loc_18000D1FF
0x18000d1f3  call    cs:__imp_CloseHandle
0x18000d1fa  nop     dword ptr [rax+rax+00h]
0x18000d1ff  mov     qword ptr [rbx+8], 0
0x18000d207  add     rsp, 20h
0x18000d20b  pop     rbx
0x18000d20c  retn
```
