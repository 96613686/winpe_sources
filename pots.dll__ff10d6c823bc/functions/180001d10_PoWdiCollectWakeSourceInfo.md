# PoWdiCollectWakeSourceInfo

- ea: `0x180001d10`
- end: `0x180001ec2`
- name: `PoWdiCollectWakeSourceInfo`
- size: `434`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800032c0`

## callees

- `0x180001d10`
- `0x180002038`
- `0x1800023a4`

## import_xrefs

- `ntdll!NtPowerInformation` at `0x180001d76`
- `ntdll!NtPowerInformation` at `0x180001d76`
- `ntdll!RtlInitUnicodeString` at `0x180001d2f`
- `ntdll!RtlInitUnicodeString` at `0x180001d3b`
- `ntdll!RtlInitUnicodeString` at `0x180001d47`
- `ntdll!RtlInitUnicodeString` at `0x180001d2f`
- `ntdll!RtlInitUnicodeString` at `0x180001d3b`
- `ntdll!RtlInitUnicodeString` at `0x180001d47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001d91`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001eac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001d91`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001eac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001d5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001d83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001d9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001e9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001d5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001d83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001d9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001e9e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001dab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001dab`

## pseudocode

```c
int __fastcall PoWdiCollectWakeSourceInfo(__int64 a1)
{
  ULONG OutputBufferLength; // esi
  HANDLE ProcessHeap; // rax
  SIZE_T i; // r8
  _DWORD *v5; // rax
  HANDLE v6; // rax
  _DWORD *v7; // rbx
  _DWORD *v8; // rcx
  _DWORD *v9; // r8
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  HANDLE v13; // rax

  *(_DWORD *)(a1 + 68) = 0;
  RtlInitUnicodeString((PUNICODE_STRING)(a1 + 72), 0);
  RtlInitUnicodeString((PUNICODE_STRING)(a1 + 88), 0);
  RtlInitUnicodeString((PUNICODE_STRING)(a1 + 104), 0);
  *(_DWORD *)(a1 + 144) = 0;
  OutputBufferLength = 1024;
  ProcessHeap = GetProcessHeap();
  for ( i = 1024; ; i = OutputBufferLength )
  {
    v5 = HeapAlloc(ProcessHeap, 0, i);
    v7 = v5;
    if ( !v5 )
      break;
    LODWORD(v5) = NtPowerInformation(SystemWakeSource, 0, 0, v5, OutputBufferLength);
    if ( (_DWORD)v5 != -1073741789 )
    {
      if ( (int)v5 < 0 || !*v7 )
      {
        if ( !v7 )
          return (int)v5;
        goto LABEL_30;
      }
      v8 = (_DWORD *)((char *)v7 + (unsigned int)v7[1]);
      if ( *v8 )
      {
        v9 = (_DWORD *)((char *)v8 + (unsigned int)v8[1]);
        if ( *v9 )
        {
          if ( *v9 == 1 )
          {
            v12 = v9[2];
            if ( v12 )
            {
              if ( v12 == 1 )
              {
                *(_DWORD *)(a1 + 4) |= 0x800u;
                *(_DWORD *)(a1 + 68) = 2;
              }
            }
            else
            {
              *(_DWORD *)(a1 + 4) |= 0x800u;
              *(_DWORD *)(a1 + 68) = 1;
            }
            goto LABEL_30;
          }
          if ( *v9 == 2 )
          {
            *(_DWORD *)(a1 + 4) |= 0x2000u;
          }
          else
          {
            if ( *v9 != 3 )
            {
              if ( *v9 == 4 )
              {
                v10 = v9[2];
                if ( v10 )
                {
                  v11 = v10 - 1;
                  if ( v11 )
                  {
                    if ( v11 == 1 )
                      *(_DWORD *)(a1 + 68) = 9;
                  }
                  else
                  {
                    *(_DWORD *)(a1 + 4) |= 0x100000u;
                    *(_DWORD *)(a1 + 68) = 4;
                  }
                }
                else
                {
                  *(_DWORD *)(a1 + 4) |= 0x10000u;
                  *(_DWORD *)(a1 + 68) = 3;
                }
              }
              goto LABEL_30;
            }
            *(_DWORD *)(a1 + 4) |= 0x40000u;
          }
          PoWdiGetTimerText(v9, a1);
        }
        else
        {
          *(_DWORD *)(a1 + 4) |= 0x1000u;
          PoWdiGetDeviceText((__int64)v9);
        }
      }
      else
      {
        *(_DWORD *)(a1 + 4) |= 0x4000000u;
      }
LABEL_30:
      v13 = GetProcessHeap();
      LODWORD(v5) = HeapFree(v13, 0, v7);
      return (int)v5;
    }
    v6 = GetProcessHeap();
    HeapFree(v6, 0, v7);
    OutputBufferLength += 1024;
    ProcessHeap = GetProcessHeap();
  }
  return (int)v5;
}

```

## disassembly

```asm
0x180001d10  mov     [rsp+arg_0], rbx
0x180001d15  mov     [rsp+arg_8], rsi
0x180001d1a  push    rdi
0x180001d1b  sub     rsp, 30h
0x180001d1f  mov     rdi, rcx
0x180001d22  mov     dword ptr [rcx+44h], 0
0x180001d29  add     rcx, 48h ; 'H'; DestinationString
0x180001d2d  xor     edx, edx; SourceString
0x180001d2f  call    cs:__imp_RtlInitUnicodeString
0x180001d35  lea     rcx, [rdi+58h]; DestinationString
0x180001d39  xor     edx, edx; SourceString
0x180001d3b  call    cs:__imp_RtlInitUnicodeString
0x180001d41  lea     rcx, [rdi+68h]; DestinationString
0x180001d45  xor     edx, edx; SourceString
0x180001d47  call    cs:__imp_RtlInitUnicodeString
0x180001d4d  mov     dword ptr [rdi+90h], 0
0x180001d57  mov     esi, 400h
0x180001d5c  call    cs:__imp_GetProcessHeap
0x180001d62  mov     r8d, esi
0x180001d65  jmp     short loc_180001DA6
0x180001d67  xor     edx, edx; InputBuffer
0x180001d69  mov     [rsp+38h+OutputBufferLength], esi; OutputBufferLength
0x180001d6d  mov     r9, rbx; OutputBuffer
0x180001d70  xor     r8d, r8d; InputBufferLength
0x180001d73  lea     ecx, [rdx+23h]; PowerInformationLevel
0x180001d76  call    cs:__imp_NtPowerInformation
0x180001d7c  cmp     eax, 0C0000023h
0x180001d81  jnz     short loc_180001DBE
0x180001d83  call    cs:__imp_GetProcessHeap
0x180001d89  mov     r8, rbx; lpMem
0x180001d8c  xor     edx, edx; dwFlags
0x180001d8e  mov     rcx, rax; hHeap
0x180001d91  call    cs:__imp_HeapFree
0x180001d97  add     esi, 400h
0x180001d9d  call    cs:__imp_GetProcessHeap
0x180001da3  mov     r8d, esi; dwBytes
0x180001da6  xor     edx, edx; dwFlags
0x180001da8  mov     rcx, rax; hHeap
0x180001dab  call    cs:__imp_HeapAlloc
0x180001db1  mov     rbx, rax
0x180001db4  test    rax, rax
0x180001db7  jnz     short loc_180001D67
0x180001db9  jmp     loc_180001EB2
0x180001dbe  test    eax, eax
0x180001dc0  js      loc_180001E99
0x180001dc6  cmp     dword ptr [rbx], 0
0x180001dc9  jz      loc_180001E99
0x180001dcf  mov     ecx, [rbx+4]
0x180001dd2  add     rcx, rbx
0x180001dd5  cmp     dword ptr [rcx], 0
0x180001dd8  jnz     short loc_180001DE4
0x180001dda  bts     dword ptr [rdi+4], 1Ah
0x180001ddf  jmp     loc_180001E9E
0x180001de4  mov     r8d, [rcx+4]
0x180001de8  add     r8, rcx
0x180001deb  mov     ecx, [r8]
0x180001dee  test    ecx, ecx
0x180001df0  jz      loc_180001E87
0x180001df6  sub     ecx, 1
0x180001df9  jz      short loc_180001E5E
0x180001dfb  sub     ecx, 1
0x180001dfe  jz      short loc_180001E4C
0x180001e00  sub     ecx, 1
0x180001e03  jz      short loc_180001E45
0x180001e05  cmp     ecx, 1
0x180001e08  jnz     loc_180001E9E
0x180001e0e  mov     ecx, [r8+8]
0x180001e12  test    ecx, ecx
0x180001e14  jz      short loc_180001E37
0x180001e16  sub     ecx, 1
0x180001e19  jz      short loc_180001E29
0x180001e1b  cmp     ecx, 1
0x180001e1e  jnz     short loc_180001E9E
0x180001e20  mov     dword ptr [rdi+44h], 9
0x180001e27  jmp     short loc_180001E9E
0x180001e29  bts     dword ptr [rdi+4], 14h
0x180001e2e  mov     dword ptr [rdi+44h], 4
0x180001e35  jmp     short loc_180001E9E
0x180001e37  bts     dword ptr [rdi+4], 10h
0x180001e3c  mov     dword ptr [rdi+44h], 3
0x180001e43  jmp     short loc_180001E9E
0x180001e45  bts     dword ptr [rdi+4], 12h
0x180001e4a  jmp     short loc_180001E51
0x180001e4c  bts     dword ptr [rdi+4], 0Dh
0x180001e51  mov     rdx, rdi
0x180001e54  mov     rcx, r8
0x180001e57  call    PoWdiGetTimerText
0x180001e5c  jmp     short loc_180001E9E
0x180001e5e  mov     ecx, [r8+8]
0x180001e62  test    ecx, ecx
0x180001e64  jz      short loc_180001E79
0x180001e66  cmp     ecx, 1
0x180001e69  jnz     short loc_180001E9E
0x180001e6b  bts     dword ptr [rdi+4], 0Bh
0x180001e70  mov     dword ptr [rdi+44h], 2
0x180001e77  jmp     short loc_180001E9E
0x180001e79  bts     dword ptr [rdi+4], 0Bh
0x180001e7e  mov     dword ptr [rdi+44h], 1
0x180001e85  jmp     short loc_180001E9E
0x180001e87  bts     dword ptr [rdi+4], 0Ch
0x180001e8c  mov     rdx, rdi
0x180001e8f  mov     rcx, r8
0x180001e92  call    PoWdiGetDeviceText
0x180001e97  jmp     short loc_180001E9E
0x180001e99  test    rbx, rbx
0x180001e9c  jz      short loc_180001EB2
0x180001e9e  call    cs:__imp_GetProcessHeap
0x180001ea4  mov     r8, rbx; lpMem
0x180001ea7  xor     edx, edx; dwFlags
0x180001ea9  mov     rcx, rax; hHeap
0x180001eac  call    cs:__imp_HeapFree
0x180001eb2  mov     rbx, [rsp+38h+arg_0]
0x180001eb7  mov     rsi, [rsp+38h+arg_8]
0x180001ebc  add     rsp, 30h
0x180001ec0  pop     rdi
0x180001ec1  retn
```
