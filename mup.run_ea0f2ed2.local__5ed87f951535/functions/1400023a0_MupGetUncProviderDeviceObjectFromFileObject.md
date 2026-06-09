# MupGetUncProviderDeviceObjectFromFileObject

- ea: `0x1400023a0`
- end: `0x140002440`
- name: `MupGetUncProviderDeviceObjectFromFileObject`
- size: `160`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x14001e6c0`
- `0x14001e6f0`
- `0x14001e7a0`
- `0x14001e830`
- `0x14001eb30`
- `0x14001eba0`
- `0x14001ec40`
- `0x14001edb0`
- `0x14001ee30`
- `0x14001ee70`
- `0x14001eef0`
- `0x14001ef30`
- `0x14001f230`

## callees

- `0x1400023a0`
- `0x140002700`

## import_xrefs

- `ntoskrnl!FsRtlLookupPerFileObjectContext` at `0x1400023be`
- `ntoskrnl!FsRtlLookupPerFileObjectContext` at `0x1400023be`

## pseudocode

```c
__int64 __fastcall MupGetUncProviderDeviceObjectFromFileObject(struct _FILE_OBJECT *a1)
{
  PFSRTL_PER_FILEOBJECT_CONTEXT v2; // rax
  PVOID *p_InstanceId; // rbx
  _QWORD *v4; // rax

  v2 = FsRtlLookupPerFileObjectContext(a1, MupDeviceObject, 0);
  if ( v2 )
    p_InstanceId = &v2[-1].InstanceId;
  else
    p_InstanceId = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids, a1, p_InstanceId);
  }
  if ( p_InstanceId && (v4 = p_InstanceId[21]) != 0 )
    return v4[21];
  else
    return 0;
}

```

## disassembly

```asm
0x1400023a0  mov     [rsp+arg_0], rbx
0x1400023a5  mov     [rsp+arg_8], rsi
0x1400023aa  push    rdi
0x1400023ab  sub     rsp, 30h
0x1400023af  mov     rdx, cs:MupDeviceObject; OwnerId
0x1400023b6  xor     r8d, r8d; InstanceId
0x1400023b9  mov     rdi, rcx
0x1400023bc  xor     esi, esi
0x1400023be  call    cs:__imp_FsRtlLookupPerFileObjectContext
0x1400023c5  nop     dword ptr [rax+rax+00h]
0x1400023ca  test    rax, rax
0x1400023cd  jz      short loc_14000241D
0x1400023cf  lea     rbx, [rax-8]
0x1400023d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400023da  lea     rax, WPP_GLOBAL_Control
0x1400023e1  cmp     rcx, rax
0x1400023e4  jz      short loc_1400023EF
0x1400023e6  test    dword ptr [rcx+2Ch], 4000000h
0x1400023ed  jnz     short loc_140002421
0x1400023ef  test    rbx, rbx
0x1400023f2  jz      short loc_140002418
0x1400023f4  mov     rax, [rbx+0A8h]
0x1400023fb  test    rax, rax
0x1400023fe  jz      short loc_140002418
0x140002400  mov     rax, [rax+0A8h]
0x140002407  mov     rbx, [rsp+38h+arg_0]
0x14000240c  mov     rsi, [rsp+38h+arg_8]
0x140002411  add     rsp, 30h
0x140002415  pop     rdi
0x140002416  retn
0x140002418  mov     rax, rsi
0x14000241b  jmp     short loc_140002407
0x14000241d  xor     ebx, ebx
0x14000241f  jmp     short loc_1400023D3
0x140002421  mov     rcx, [rcx+18h]
0x140002425  lea     r8, WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids
0x14000242c  mov     edx, 0Eh
0x140002431  mov     [rsp+38h+var_18], rbx
0x140002436  mov     r9, rdi
0x140002439  call    WPP_SF_qq
0x14000243e  jmp     short loc_1400023EF
```
