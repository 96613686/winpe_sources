# NgcUtils::CoMemResourceStringAllocCopy(HINSTANCE__ *,uint,ushort * *)

- ea: `0x1800128a4`
- end: `0x180012904`
- name: `?CoMemResourceStringAllocCopy@NgcUtils@@YAJPEAUHINSTANCE__@@IPEAPEAG@Z`
- size: `96`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, HINSTANCE, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010550`

## callees

- `0x1800128a4`
- `0x18001290c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800128e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800128e7`

## pseudocode

```c
__int64 __fastcall NgcUtils::CoMemResourceStringAllocCopy(
        NgcUtils *this,
        HINSTANCE a2,
        LPVOID *a3,
        unsigned __int16 **a4)
{
  int v6; // ebx
  LPVOID pv; // [rsp+40h] [rbp+18h] BYREF

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  pv = 0;
  v6 = NgcUtils::CoMemResourceStringAllocCopyInternal(this, a2, &pv, a4);
  if ( v6 >= 0 )
  {
    *a3 = pv;
  }
  else if ( pv )
  {
    CoTaskMemFree(pv);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800128a4  mov     [rsp+arg_0], rbx
0x1800128a9  push    rdi
0x1800128aa  sub     rsp, 20h
0x1800128ae  mov     rdi, r8
0x1800128b1  test    r8, r8
0x1800128b4  jnz     short loc_1800128BD
0x1800128b6  mov     eax, 80004003h
0x1800128bb  jmp     short loc_1800128F9
0x1800128bd  mov     qword ptr [r8], 0
0x1800128c4  lea     r8, [rsp+28h+pv]
0x1800128c9  mov     [rsp+28h+pv], 0
0x1800128d2  call    NgcUtils__CoMemResourceStringAllocCopyInternal
0x1800128d7  mov     ebx, eax
0x1800128d9  test    eax, eax
0x1800128db  jns     short loc_1800128EF
0x1800128dd  mov     rcx, [rsp+28h+pv]; pv
0x1800128e2  test    rcx, rcx
0x1800128e5  jz      short loc_1800128F7
0x1800128e7  call    cs:__imp_CoTaskMemFree
0x1800128ed  jmp     short loc_1800128F7
0x1800128ef  mov     rax, [rsp+28h+pv]
0x1800128f4  mov     [rdi], rax
0x1800128f7  mov     eax, ebx
0x1800128f9  mov     rbx, [rsp+28h+arg_0]
0x1800128fe  add     rsp, 20h
0x180012902  pop     rdi
0x180012903  retn
```
