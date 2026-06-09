# CMCreateMultiProfileTransform

- ea: `0x180006770`
- end: `0x1800067db`
- name: `CMCreateMultiProfileTransform`
- size: `107`
- prototype: `HCMTRANSFORM __stdcall(PHPROFILE pahProfiles, DWORD nProfiles, PDWORD padwIntents, DWORD nIntents, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002344`
- `0x180006770`
- `0x1800067e4`
- `0x1800069f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800067aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800067aa`

## pseudocode

```c
HCMTRANSFORM __stdcall CMCreateMultiProfileTransform(
        PHPROFILE pahProfiles,
        DWORD nProfiles,
        PDWORD padwIntents,
        DWORD nIntents,
        DWORD dwFlags)
{
  DWORD v5; // eax
  unsigned __int8 v6; // bl
  void *v8; // rbx
  _QWORD v9[3]; // [rsp+40h] [rbp-18h] BYREF

  v9[0] = 0;
  v5 = CMCreateMultiProfileTransformInternal(v9, (__int64)pahProfiles, nProfiles, padwIntents, nIntents, dwFlags);
  v6 = v5;
  if ( v5 )
  {
    SetLastError(v5);
    return (HCMTRANSFORM)v6;
  }
  else
  {
    v8 = (void *)StoreTransform(v9[0]);
    if ( v8 == (void *)8 )
      LHColorWorldClose(v9[0]);
    return v8;
  }
}

```

## disassembly

```asm
0x180006770  push    rbx
0x180006772  sub     rsp, 50h
0x180006776  mov     eax, [rsp+58h+dwFlags]
0x18000677d  mov     [rsp+58h+var_30], eax
0x180006781  mov     [rsp+58h+var_38], r9d
0x180006786  mov     r9, r8
0x180006789  mov     r8d, edx
0x18000678c  mov     [rsp+58h+var_18], 0
0x180006795  mov     rdx, rcx
0x180006798  lea     rcx, [rsp+58h+var_18]
0x18000679d  call    CMCreateMultiProfileTransformInternal
0x1800067a2  mov     ebx, eax
0x1800067a4  test    eax, eax
0x1800067a6  jz      short loc_1800067B5
0x1800067a8  mov     ecx, ebx; dwErrCode
0x1800067aa  call    cs:__imp_SetLastError
0x1800067b0  movzx   eax, bl
0x1800067b3  jmp     short loc_1800067D5
0x1800067b5  mov     rcx, [rsp+58h+var_18]
0x1800067ba  call    StoreTransform
0x1800067bf  mov     rbx, rax
0x1800067c2  cmp     rax, 8
0x1800067c6  jnz     short loc_1800067D2
0x1800067c8  mov     rcx, [rsp+58h+var_18]
0x1800067cd  call    LHColorWorldClose
0x1800067d2  mov     rax, rbx
0x1800067d5  add     rsp, 50h
0x1800067d9  pop     rbx
0x1800067da  retn
```
