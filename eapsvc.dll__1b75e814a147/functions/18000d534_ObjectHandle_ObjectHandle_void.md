# ObjectHandle::~ObjectHandle(void)

- ea: `0x18000d534`
- end: `0x18000d569`
- name: `??1ObjectHandle@@UEAA@XZ`
- size: `53`
- prototype: `void __fastcall(ObjectHandle *__hidden this)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a978`
- `0x18000aa48`
- `0x18000aac4`
- `0x18000ac00`
- `0x18000d570`
- `0x18000e188`
- `0x18001064c`
- `0x1800153f9`
- `0x1800154ab`
- `0x180015664`
- `0x180015884`

## callees

- `0x18000d534`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d555`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d555`

## pseudocode

```c
void __fastcall ObjectHandle::~ObjectHandle(ObjectHandle *this)
{
  char *v2; // rcx

  *(_QWORD *)this = &ObjectHandle::`vftable';
  v2 = (char *)*((_QWORD *)this + 1);
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v2);
  *((_QWORD *)this + 1) = 0;
}

```

## disassembly

```asm
0x18000d534  push    rbx
0x18000d536  sub     rsp, 20h
0x18000d53a  lea     rax, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x18000d541  mov     rbx, rcx
0x18000d544  mov     [rcx], rax
0x18000d547  mov     rcx, [rcx+8]; hObject
0x18000d54b  lea     rax, [rcx-1]
0x18000d54f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d553  ja      short loc_18000D55B
0x18000d555  call    cs:__imp_CloseHandle
0x18000d55b  mov     qword ptr [rbx+8], 0
0x18000d563  add     rsp, 20h
0x18000d567  pop     rbx
0x18000d568  retn
```
