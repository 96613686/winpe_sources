# CMCreateDeviceLinkProfile

- ea: `0x18001d680`
- end: `0x18001d76b`
- name: `CMCreateDeviceLinkProfile`
- size: `235`
- prototype: `BOOL __stdcall(PHPROFILE pahProfiles, DWORD nProfiles, PDWORD padwIntents, DWORD nIntents, DWORD dwFlags, LPBYTE *lpProfileData)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180002344`
- `0x1800042e0`
- `0x1800067e4`
- `0x180018b28`
- `0x18001d680`
- `0x18001e1ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d755`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d755`

## pseudocode

```c
BOOL __stdcall CMCreateDeviceLinkProfile(
        PHPROFILE pahProfiles,
        DWORD nProfiles,
        PDWORD padwIntents,
        DWORD nIntents,
        DWORD dwFlags,
        LPBYTE *lpProfileData)
{
  DWORD v9; // eax
  DWORD v10; // ecx
  _WORD *v11; // rdi
  DWORD v12; // ecx
  __int64 v13; // rdx
  DWORD v14; // ebx
  __int16 v16; // [rsp+40h] [rbp-48h] BYREF
  __int64 v17[8]; // [rsp+48h] [rbp-40h] BYREF

  v16 = 0;
  v17[0] = 0;
  *lpProfileData = 0;
  v9 = CMCreateMultiProfileTransformInternal(v17, (__int64)pahProfiles, nProfiles, padwIntents, nIntents, dwFlags);
  if ( v9 )
  {
    v10 = v9;
  }
  else
  {
    v11 = (_WORD *)SmartNewPtrClear(8 * nProfiles + 16, &v16);
    if ( v16 )
    {
      v14 = v16;
    }
    else
    {
      *v11 = 0;
      v12 = 0;
      for ( v11[1] = nProfiles; v12 < nProfiles; *(_QWORD *)&v11[4 * v13 + 4] = pahProfiles[v13] )
        v13 = v12++;
      v14 = DeviceLinkFill(v17[0], (__int64)v11, (unsigned int **)lpProfileData, *padwIntents);
      DisposeIfPtr(v11);
      if ( !v14 )
      {
        LHColorWorldClose(v17[0]);
        return 1;
      }
    }
    LHColorWorldClose(v17[0]);
    v10 = v14;
  }
  SetLastError(v10);
  return 0;
}

```

## disassembly

```asm
0x18001d680  mov     r11, rsp
0x18001d683  push    rbx
0x18001d684  push    rbp
0x18001d685  push    rdi
0x18001d686  push    r12
0x18001d688  push    r14
0x18001d68a  push    r15
0x18001d68c  sub     rsp, 58h
0x18001d690  mov     eax, [rsp+88h+dwFlags]
0x18001d697  xor     r12d, r12d
0x18001d69a  mov     rbp, [rsp+88h+lpProfileData]
0x18001d6a2  mov     r15, r8
0x18001d6a5  mov     [rsp+88h+var_60], eax
0x18001d6a9  mov     ebx, edx
0x18001d6ab  mov     [r11-68h], r9d
0x18001d6af  mov     r14, rcx
0x18001d6b2  mov     r9, r8
0x18001d6b5  mov     [r11-48h], r12w
0x18001d6ba  mov     r8d, edx
0x18001d6bd  mov     [r11-40h], r12
0x18001d6c1  mov     rdx, rcx
0x18001d6c4  mov     [rbp+0], r12
0x18001d6c8  lea     rcx, [r11-40h]
0x18001d6cc  call    CMCreateMultiProfileTransformInternal
0x18001d6d1  test    eax, eax
0x18001d6d3  jz      short loc_18001D6D9
0x18001d6d5  mov     ecx, eax
0x18001d6d7  jmp     short loc_18001D755
0x18001d6d9  lea     ecx, ds:10h[rbx*8]
0x18001d6e0  lea     rdx, [rsp+88h+var_48]
0x18001d6e5  call    SmartNewPtrClear
0x18001d6ea  mov     rdi, rax
0x18001d6ed  movsx   eax, [rsp+88h+var_48]
0x18001d6f2  test    ax, ax
0x18001d6f5  jnz     short loc_18001D747
0x18001d6f7  mov     [rdi], r12w
0x18001d6fb  mov     ecx, r12d
0x18001d6fe  mov     [rdi+2], bx
0x18001d702  test    ebx, ebx
0x18001d704  jz      short loc_18001D717
0x18001d706  mov     edx, ecx
0x18001d708  inc     ecx
0x18001d70a  mov     rax, [r14+rdx*8]
0x18001d70e  mov     [rdi+rdx*8+8], rax
0x18001d713  cmp     ecx, ebx
0x18001d715  jb      short loc_18001D706
0x18001d717  mov     r9d, [r15]
0x18001d71a  mov     r8, rbp
0x18001d71d  mov     rcx, [rsp+88h+var_40]
0x18001d722  mov     rdx, rdi
0x18001d725  call    DeviceLinkFill
0x18001d72a  mov     rcx, rdi
0x18001d72d  mov     ebx, eax
0x18001d72f  call    DisposeIfPtr
0x18001d734  test    ebx, ebx
0x18001d736  jnz     short loc_18001D749
0x18001d738  mov     rcx, [rsp+88h+var_40]
0x18001d73d  call    LHColorWorldClose
0x18001d742  lea     eax, [rbx+1]
0x18001d745  jmp     short loc_18001D75D
0x18001d747  mov     ebx, eax
0x18001d749  mov     rcx, [rsp+88h+var_40]
0x18001d74e  call    LHColorWorldClose
0x18001d753  mov     ecx, ebx; dwErrCode
0x18001d755  call    cs:__imp_SetLastError
0x18001d75b  xor     eax, eax
0x18001d75d  add     rsp, 58h
0x18001d761  pop     r15
0x18001d763  pop     r14
0x18001d765  pop     r12
0x18001d767  pop     rdi
0x18001d768  pop     rbp
0x18001d769  pop     rbx
0x18001d76a  retn
```
