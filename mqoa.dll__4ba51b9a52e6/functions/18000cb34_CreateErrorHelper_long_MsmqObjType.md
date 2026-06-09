# CreateErrorHelper(long,MsmqObjType)

- ea: `0x18000cb34`
- end: `0x18000cb60`
- name: `?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z`
- size: `44`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `183`
- callee_count: `2`
- tags: ``

## callers

- `0x180004040`
- `0x180004230`
- `0x180005880`
- `0x180005980`
- `0x180006c40`
- `0x180007aa0`
- `0x1800083a0`
- `0x180008420`
- `0x180008480`
- `0x180008520`
- `0x1800085c0`
- `0x180008660`
- `0x1800086a0`
- `0x1800086e0`
- `0x180008720`
- `0x180008860`
- `0x1800088e0`
- `0x180008960`
- `0x18000a700`
- `0x180013eb0`
- `0x180013f10`
- `0x1800147bc`
- `0x1800155cc`
- `0x1800158dc`
- `0x180015a64`
- `0x1800160e4`
- `0x180016560`
- `0x180017020`
- `0x180017d10`
- `0x180017da0`
- `0x180017e30`
- `0x180017fc0`
- `0x1800180f0`
- `0x1800181f0`
- `0x180018270`
- `0x1800182d0`
- `0x180018390`
- `0x180018410`
- `0x1800184a0`
- `0x180018570`
- `0x180018640`
- `0x180018920`
- `0x1800189d0`
- `0x180018c00`
- `0x180018ca0`
- `0x180018d20`
- `0x180018db0`
- `0x180018e40`
- `0x180018ed0`
- `0x180018f50`

## callees

- `0x18000cb34`
- `0x18002678c`

## pseudocode

```c
__int64 __fastcall CreateErrorHelper(signed int a1, int a2)
{
  if ( a1 < 0 )
    return (unsigned int)CreateError(
                           a1,
                           (struct _GUID *)*(&g_rgObjInfo + 2 * a2 + 1),
                           (const char *)*(&g_rgObjInfo + 2 * a2));
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x18000cb34  sub     rsp, 28h
0x18000cb38  test    ecx, ecx
0x18000cb3a  jns     short loc_18000CB59
0x18000cb3c  movsxd  rdx, edx
0x18000cb3f  lea     rax, ?g_rgObjInfo@@3PAUMsmqObjInfo@@A; MsmqObjInfo near * g_rgObjInfo
0x18000cb46  add     rdx, rdx
0x18000cb49  mov     r8, [rax+rdx*8]; char *
0x18000cb4d  mov     rdx, [rax+rdx*8+8]; struct _GUID *
0x18000cb52  call    ?CreateError@@YAJJPEAU_GUID@@PEBD@Z; CreateError(long,_GUID *,char const *)
0x18000cb57  mov     ecx, eax
0x18000cb59  mov     eax, ecx
0x18000cb5b  add     rsp, 28h
0x18000cb5f  retn
```
