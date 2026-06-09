# GetDeviceRemovalTimeoutPolicyPeriod

- ea: `0x180004460`
- end: `0x1800045b1`
- name: `GetDeviceRemovalTimeoutPolicyPeriod`
- size: `337`
- prototype: `__int64 __fastcall(__int64, void *, __int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180004e74`

## callees

- `0x180004460`
- `0x180008e30`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000453f`
- `msvcrt!_wcsicmp` at `0x18000455b`
- `msvcrt!_wcsicmp` at `0x18000453f`
- `msvcrt!_wcsicmp` at `0x18000455b`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x1800044dd`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x1800044dd`

## pseudocode

```c
__int64 __fastcall GetDeviceRemovalTimeoutPolicyPeriod(__int64 a1, void *a2, __int64 a3, int a4)
{
  __int64 v4; // rdi
  unsigned int v7; // esi
  __int64 v8; // rbx
  GUID *v9; // rcx
  DEVPROPTYPE PropertyType; // [rsp+40h] [rbp-1D8h] BYREF
  DWORD RequiredSize[3]; // [rsp+44h] [rbp-1D4h] BYREF
  wchar_t PropertyBuffer[200]; // [rsp+50h] [rbp-1C8h] BYREF

  v4 = *(unsigned int *)(a1 + 76);
  PropertyType = 0;
  RequiredSize[0] = 0;
  if ( SetupDiGetDevicePropertyW(
         a2,
         (PSP_DEVINFO_DATA)a3,
         &DEVPKEY_Device_EnumeratorName,
         &PropertyType,
         (PBYTE)PropertyBuffer,
         0x190u,
         RequiredSize,
         0)
    && PropertyType == 18 )
  {
    v7 = 0;
    while ( 1 )
    {
      v8 = 4LL * v7;
      v9 = (&off_18000B1F0)[v8];
      if ( *(_QWORD *)&v9->Data1 == *(_QWORD *)(a3 + 4)
        && *(_QWORD *)v9->Data4 == *(_QWORD *)(a3 + 12)
        && ((*(_BYTE *)(&off_18000B1F0 + v8 + 3) & 1) == 0 || *((_DWORD *)&off_18000B1F0 + 2 * v8 + 2) == a4)
        && ((*(_BYTE *)(&off_18000B1F0 + v8 + 3) & 2) == 0
         || !_wcsicmp((const wchar_t *)*(&off_18000B1F0 + v8 + 2), PropertyBuffer))
        && ((*(_BYTE *)(&off_18000B1F0 + v8 + 3) & 4) == 0
         || _wcsicmp((const wchar_t *)*(&off_18000B1F0 + v8 + 2), PropertyBuffer)) )
      {
        break;
      }
      if ( ++v7 )
        return 864000000000LL * v4;
    }
    v4 = *((unsigned int *)&off_18000B1F0 + 8 * v7 + 7);
  }
  return 864000000000LL * v4;
}

```

## disassembly

```asm
0x180004460  mov     [rsp+arg_0], rbx
0x180004465  mov     [rsp+arg_18], rbp
0x18000446a  push    rsi
0x18000446b  push    rdi
0x18000446c  push    r12
0x18000446e  push    r14
0x180004470  push    r15
0x180004472  sub     rsp, 1F0h
0x180004479  mov     rax, cs:__security_cookie
0x180004480  xor     rax, rsp
0x180004483  mov     [rsp+218h+var_38], rax
0x18000448b  mov     edi, [rcx+4Ch]
0x18000448e  mov     r14, r8
0x180004491  mov     [rsp+218h+Flags], 0; Flags
0x180004499  lea     rcx, [rsp+218h+var_1D4]
0x18000449e  mov     [rsp+218h+RequiredSize], rcx; RequiredSize
0x1800044a3  lea     r8, DEVPKEY_Device_EnumeratorName; PropertyKey
0x1800044aa  mov     rax, rdx
0x1800044ad  mov     [rsp+218h+PropertyBufferSize], 190h; PropertyBufferSize
0x1800044b5  lea     rcx, [rsp+218h+var_1C8]
0x1800044ba  mov     [rsp+218h+PropertyType], 0
0x1800044c2  mov     [rsp+218h+PropertyBuffer], rcx; PropertyBuffer
0x1800044c7  mov     r15d, r9d
0x1800044ca  mov     rcx, rax; DeviceInfoSet
0x1800044cd  mov     [rsp+218h+var_1D4], 0
0x1800044d5  lea     r9, [rsp+218h+PropertyType]; PropertyType
0x1800044da  mov     rdx, r14; DeviceInfoData
0x1800044dd  call    cs:__imp_SetupDiGetDevicePropertyW
0x1800044e3  test    eax, eax
0x1800044e5  jz      loc_180004577
0x1800044eb  cmp     [rsp+218h+PropertyType], 12h
0x1800044f0  jnz     loc_180004577
0x1800044f6  xor     esi, esi
0x1800044f8  lea     r12, off_18000B1F0
0x1800044ff  mov     ebx, esi
0x180004501  shl     rbx, 5
0x180004505  mov     ebp, esi
0x180004507  mov     rcx, [rbx+r12]
0x18000450b  mov     rax, [rcx]
0x18000450e  cmp     rax, [r14+4]
0x180004512  jnz     short loc_180004565
0x180004514  mov     rax, [rcx+8]
0x180004518  cmp     rax, [r14+0Ch]
0x18000451c  jnz     short loc_180004565
0x18000451e  test    byte ptr [rbx+r12+18h], 1
0x180004524  jz      short loc_18000452D
0x180004526  cmp     [rbx+r12+8], r15d
0x18000452b  jnz     short loc_180004565
0x18000452d  test    byte ptr [rbx+r12+18h], 2
0x180004533  jz      short loc_180004549
0x180004535  mov     rcx, [rbx+r12+10h]; String1
0x18000453a  lea     rdx, [rsp+218h+var_1C8]; String2
0x18000453f  call    cs:__imp__wcsicmp
0x180004545  test    eax, eax
0x180004547  jnz     short loc_180004565
0x180004549  test    byte ptr [rbx+r12+18h], 4
0x18000454f  jz      short loc_18000456E
0x180004551  mov     rcx, [rbx+r12+10h]; String1
0x180004556  lea     rdx, [rsp+218h+var_1C8]; String2
0x18000455b  call    cs:__imp__wcsicmp
0x180004561  test    eax, eax
0x180004563  jnz     short loc_18000456E
0x180004565  inc     esi
0x180004567  cmp     esi, 1
0x18000456a  jb      short loc_1800044FF
0x18000456c  jmp     short loc_180004577
0x18000456e  shl     rbp, 5
0x180004572  mov     edi, [r12+rbp+1Ch]
0x180004577  mov     rax, 0C92A69C000h
0x180004581  imul    rax, rdi
0x180004585  mov     rcx, [rsp+218h+var_38]
0x18000458d  xor     rcx, rsp; StackCookie
0x180004590  call    __security_check_cookie
0x180004595  lea     r11, [rsp+218h+var_28]
0x18000459d  mov     rbx, [r11+30h]
0x1800045a1  mov     rbp, [r11+48h]
0x1800045a5  mov     rsp, r11
0x1800045a8  pop     r15
0x1800045aa  pop     r14
0x1800045ac  pop     r12
0x1800045ae  pop     rdi
0x1800045af  pop     rsi
0x1800045b0  retn
```
