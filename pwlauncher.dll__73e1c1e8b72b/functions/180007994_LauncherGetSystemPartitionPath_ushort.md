# LauncherGetSystemPartitionPath(ushort *)

- ea: `0x180007994`
- end: `0x180007c70`
- name: `?LauncherGetSystemPartitionPath@@YAHPEAG@Z`
- size: `732`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800077f8`

## callees

- `0x180005528`
- `0x180007994`
- `0x180008ac8`
- `0x180008cf0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180007aa3`
- `KERNEL32!GetProcessHeap` at `0x180007bed`
- `KERNEL32!GetProcessHeap` at `0x180007aa3`
- `KERNEL32!GetProcessHeap` at `0x180007bed`
- `KERNEL32!HeapAlloc` at `0x180007ab1`
- `KERNEL32!HeapAlloc` at `0x180007ab1`
- `KERNEL32!GetLastError` at `0x180007c1b`
- `KERNEL32!GetLastError` at `0x180007c1b`
- `KERNEL32!HeapFree` at `0x180007bfb`
- `KERNEL32!HeapFree` at `0x180007bfb`
- `KERNEL32!SetLastError` at `0x180007c03`
- `KERNEL32!SetLastError` at `0x180007c03`
- `ntdll!NtQuerySystemInformation` at `0x180007a40`
- `ntdll!NtQuerySystemInformation` at `0x180007b05`
- `ntdll!NtQuerySystemInformation` at `0x180007a40`
- `ntdll!NtQuerySystemInformation` at `0x180007b05`
- `ntdll!RtlNtStatusToDosError` at `0x180007a51`
- `ntdll!RtlNtStatusToDosError` at `0x180007b13`
- `ntdll!RtlNtStatusToDosError` at `0x180007a51`
- `ntdll!RtlNtStatusToDosError` at `0x180007b13`

## string_xrefs

- `0x180007a1c`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`
- `0x180007a77`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`
- `0x180007b4a`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`

## pseudocode

```c
__int64 __fastcall LauncherGetSystemPartitionPath(unsigned __int16 *a1)
{
  unsigned int v2; // r14d
  _QWORD *v3; // rcx
  DWORD v4; // edi
  NTSTATUS v5; // eax
  char v6; // bl
  ULONG v7; // ebx
  HANDLE ProcessHeap; // rax
  _QWORD *v9; // rax
  _QWORD *v10; // rbp
  int v11; // eax
  char v12; // bl
  __int64 v13; // rdx
  unsigned __int16 *v14; // rcx
  unsigned __int64 v15; // rax
  unsigned __int16 *v16; // rcx
  HANDLE v17; // rax
  int v18; // r8d
  int v19; // r9d
  const char *v20; // rcx
  char LastError; // [rsp+30h] [rbp-58h]
  ULONG ReturnLength; // [rsp+90h] [rbp+8h] BYREF

  v2 = 0;
  ReturnLength = 0;
  v3 = WPP_GLOBAL_Control;
  v4 = 8;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_a14d398675a93d8a8179cf1378ada974_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    v5 = NtQuerySystemInformation(MaxSystemInfoClass, 0, 0, &ReturnLength);
    v6 = v5;
    if ( v5 == -1073741789 )
    {
      v7 = ReturnLength;
      ProcessHeap = GetProcessHeap();
      v9 = HeapAlloc(ProcessHeap, 8u, v7);
      v10 = v9;
      if ( v9 )
      {
        v11 = NtQuerySystemInformation(MaxSystemInfoClass, v9, ReturnLength, &ReturnLength);
        v12 = v11;
        if ( v11 >= 0 )
        {
          v13 = 261;
          v14 = (unsigned __int16 *)v10[1];
          v15 = (unsigned __int64)*(unsigned __int16 *)v10 >> 1;
          do
          {
            if ( !v15 )
              break;
            if ( !*v14 )
              break;
            *a1++ = *v14++;
            --v15;
            --v13;
          }
          while ( v13 );
          v16 = a1 - 1;
          if ( v13 )
            v16 = a1;
          *v16 = 0;
          if ( v13 )
          {
            v4 = 0;
            v2 = 1;
          }
          else
          {
            v4 = 1359;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sdD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                22,
                (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
                (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
                7,
                v13 == 0 ? 0x7A : 0);
          }
        }
        else
        {
          v4 = RtlNtStatusToDosError(v11);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sdD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              21,
              (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
              (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
              252,
              v12);
        }
        v17 = GetProcessHeap();
        HeapFree(v17, 0, v10);
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
          243,
          8);
      }
    }
    else
    {
      v4 = RtlNtStatusToDosError(v5);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
          234,
          v6);
    }
  }
  else
  {
    v4 = 87;
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 1) != 0 )
      WPP_SF_sdD(
        v3[2],
        18,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        223,
        87);
  }
  SetLastError(v4);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    LastError = GetLastError();
    v20 = "Success";
    if ( !v2 )
      v20 = "Failure";
    WPP_SF_sdsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v18, v19, 24, (__int64)v20, LastError);
  }
  return v2;
}

```

## disassembly

```asm
0x180007994  mov     rax, rsp
0x180007997  push    rbx
0x180007998  push    rbp
0x180007999  push    rsi
0x18000799a  push    rdi
0x18000799b  push    r12
0x18000799d  push    r13
0x18000799f  push    r14
0x1800079a1  push    r15
0x1800079a3  sub     rsp, 48h
0x1800079a7  xor     r15d, r15d
0x1800079aa  mov     rsi, rcx
0x1800079ad  mov     r14d, r15d
0x1800079b0  mov     [rax+8], r15d
0x1800079b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800079bb  lea     r12, WPP_GLOBAL_Control
0x1800079c2  lea     edi, [r15+8]
0x1800079c6  lea     r13, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x1800079cd  cmp     rcx, r12
0x1800079d0  jz      short loc_1800079EE
0x1800079d2  test    [rcx+1Ch], dil
0x1800079d6  jz      short loc_1800079EE
0x1800079d8  mov     rcx, [rcx+10h]
0x1800079dc  lea     edx, [rdi+9]
0x1800079df  mov     r8, r13
0x1800079e2  call    WPP_SF_
0x1800079e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800079ee  test    rsi, rsi
0x1800079f1  jnz     short loc_180007A30
0x1800079f3  lea     edi, [rsi+57h]
0x1800079f6  cmp     rcx, r12
0x1800079f9  jz      loc_180007C01
0x1800079ff  test    byte ptr [rcx+1Ch], 1
0x180007a03  jz      loc_180007C01
0x180007a09  mov     dword ptr [rsp+88h+var_60], edi
0x180007a0d  lea     edx, [rsi+12h]
0x180007a10  mov     [rsp+88h+var_68], 0DFh
0x180007a18  mov     rcx, [rcx+10h]
0x180007a1c  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x180007a23  mov     r8, r13
0x180007a26  call    WPP_SF_sdD
0x180007a2b  jmp     loc_180007C01
0x180007a30  xor     edx, edx; SystemInformation
0x180007a32  lea     r9, [rsp+88h+ReturnLength]; ReturnLength
0x180007a3a  xor     r8d, r8d; SystemInformationLength
0x180007a3d  lea     ecx, [rdx+62h]; SystemInformationClass
0x180007a40  call    cs:__imp_NtQuerySystemInformation
0x180007a46  mov     ebx, eax
0x180007a48  cmp     eax, 0C0000023h
0x180007a4d  jz      short loc_180007A9C
0x180007a4f  mov     ecx, eax; Status
0x180007a51  call    cs:__imp_RtlNtStatusToDosError
0x180007a57  mov     edi, eax
0x180007a59  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a60  cmp     rcx, r12
0x180007a63  jz      loc_180007C01
0x180007a69  test    byte ptr [rcx+1Ch], 1
0x180007a6d  jz      loc_180007C01
0x180007a73  mov     rcx, [rcx+10h]
0x180007a77  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x180007a7e  mov     edx, 13h
0x180007a83  mov     dword ptr [rsp+88h+var_60], ebx
0x180007a87  mov     r8, r13
0x180007a8a  mov     [rsp+88h+var_68], 0EAh
0x180007a92  call    WPP_SF_sdD
0x180007a97  jmp     loc_180007C01
0x180007a9c  mov     ebx, [rsp+88h+ReturnLength]
0x180007aa3  call    cs:__imp_GetProcessHeap
0x180007aa9  mov     r8d, ebx; dwBytes
0x180007aac  mov     edx, edi; dwFlags
0x180007aae  mov     rcx, rax; hHeap
0x180007ab1  call    cs:__imp_HeapAlloc
0x180007ab7  mov     rbp, rax
0x180007aba  test    rax, rax
0x180007abd  jnz     short loc_180007AED
0x180007abf  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ac6  cmp     rcx, r12
0x180007ac9  jz      loc_180007C01
0x180007acf  test    byte ptr [rcx+1Ch], 1
0x180007ad3  jz      loc_180007C01
0x180007ad9  mov     dword ptr [rsp+88h+var_60], edi
0x180007add  lea     edx, [rax+14h]
0x180007ae0  mov     [rsp+88h+var_68], 0F3h
0x180007ae8  jmp     loc_180007A18
0x180007aed  mov     r8d, [rsp+88h+ReturnLength]; SystemInformationLength
0x180007af5  lea     r9, [rsp+88h+ReturnLength]; ReturnLength
0x180007afd  mov     rdx, rbp; SystemInformation
0x180007b00  mov     ecx, 62h ; 'b'; SystemInformationClass
0x180007b05  call    cs:__imp_NtQuerySystemInformation
0x180007b0b  mov     ebx, eax
0x180007b0d  test    eax, eax
0x180007b0f  jns     short loc_180007B5E
0x180007b11  mov     ecx, eax; Status
0x180007b13  call    cs:__imp_RtlNtStatusToDosError
0x180007b19  mov     edi, eax
0x180007b1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b22  cmp     rcx, r12
0x180007b25  jz      loc_180007BED
0x180007b2b  test    byte ptr [rcx+1Ch], 1
0x180007b2f  jz      loc_180007BED
0x180007b35  mov     dword ptr [rsp+88h+var_60], ebx
0x180007b39  mov     edx, 15h
0x180007b3e  mov     [rsp+88h+var_68], 0FCh
0x180007b46  mov     rcx, [rcx+10h]
0x180007b4a  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x180007b51  mov     r8, r13
0x180007b54  call    WPP_SF_sdD
0x180007b59  jmp     loc_180007BED
0x180007b5e  movzx   eax, word ptr [rbp+0]
0x180007b62  mov     edx, 105h
0x180007b67  mov     rcx, [rbp+8]
0x180007b6b  shr     rax, 1
0x180007b6e  test    rax, rax
0x180007b71  jz      short loc_180007B92
0x180007b73  movzx   r8d, word ptr [rcx]
0x180007b77  test    r8w, r8w
0x180007b7b  jz      short loc_180007B92
0x180007b7d  mov     [rsi], r8w
0x180007b81  add     rcx, 2
0x180007b85  add     rsi, 2
0x180007b89  dec     rax
0x180007b8c  sub     rdx, 1
0x180007b90  jnz     short loc_180007B6E
0x180007b92  mov     rax, rdx
0x180007b95  lea     rcx, [rsi-2]
0x180007b99  neg     rax
0x180007b9c  sbb     r8d, r8d
0x180007b9f  not     r8d
0x180007ba2  and     r8d, 8007007Ah
0x180007ba9  test    rdx, rdx
0x180007bac  cmovnz  rcx, rsi
0x180007bb0  mov     [rcx], r15w
0x180007bb4  jnz     short loc_180007BE4
0x180007bb6  mov     edi, 54Fh
0x180007bbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180007bc2  cmp     rcx, r12
0x180007bc5  jz      short loc_180007BED
0x180007bc7  test    byte ptr [rcx+1Ch], 1
0x180007bcb  jz      short loc_180007BED
0x180007bcd  mov     dword ptr [rsp+88h+var_60], r8d
0x180007bd2  mov     edx, 16h
0x180007bd7  mov     [rsp+88h+var_68], 107h
0x180007bdf  jmp     loc_180007B46
0x180007be4  mov     edi, r15d
0x180007be7  mov     r14d, 1
0x180007bed  call    cs:__imp_GetProcessHeap
0x180007bf3  mov     r8, rbp; lpMem
0x180007bf6  xor     edx, edx; dwFlags
0x180007bf8  mov     rcx, rax; hHeap
0x180007bfb  call    cs:__imp_HeapFree
0x180007c01  mov     ecx, edi; dwErrCode
0x180007c03  call    cs:__imp_SetLastError
0x180007c09  mov     rax, cs:WPP_GLOBAL_Control
0x180007c10  cmp     rax, r12
0x180007c13  jz      short loc_180007C5C
0x180007c15  test    byte ptr [rax+1Ch], 4
0x180007c19  jz      short loc_180007C5C
0x180007c1b  call    cs:__imp_GetLastError
0x180007c21  lea     rdx, aFailure; "Failure"
0x180007c28  mov     dword ptr [rsp+88h+var_58], eax
0x180007c2c  test    r14d, r14d
0x180007c2f  lea     rcx, aSuccess; "Success"
0x180007c36  cmovz   rcx, rdx
0x180007c3a  mov     edx, 17h
0x180007c3f  mov     [rsp+88h+var_60], rcx
0x180007c44  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c4b  mov     [rsp+88h+var_68], 118h
0x180007c53  mov     rcx, [rcx+10h]
0x180007c57  call    WPP_SF_sdsd
0x180007c5c  mov     eax, r14d
0x180007c5f  add     rsp, 48h
0x180007c63  pop     r15
0x180007c65  pop     r14
0x180007c67  pop     r13
0x180007c69  pop     r12
0x180007c6b  pop     rdi
0x180007c6c  pop     rsi
0x180007c6d  pop     rbp
0x180007c6e  pop     rbx
0x180007c6f  retn
```
