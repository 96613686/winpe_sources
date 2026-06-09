# PoWdiGetDeviceText

- ea: `0x180002038`
- end: `0x1800022d3`
- name: `PoWdiGetDeviceText`
- size: `667`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001d10`

## callees

- `0x180002038`
- `0x1800048f6`
- `0x180004930`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180002274`
- `ntdll!RtlInitUnicodeString` at `0x180002274`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800021e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002293`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800021e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002293`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000207d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800021da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800021f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002285`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000207d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800021da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800021f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002285`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000208b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002205`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000208b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002205`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18000213d`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18000213d`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1800022a5`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1800022a5`

## pseudocode

```c
int __fastcall PoWdiGetDeviceText(__int64 a1)
{
  unsigned __int64 v1; // rdi
  HANDLE ProcessHeap; // rax
  _WORD *v4; // rax
  void *v5; // r15
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rdi
  _WORD *v8; // rcx
  _WORD *v9; // rcx
  HANDLE v10; // rax

  v1 = *(unsigned __int16 *)(a1 + 8);
  ProcessHeap = GetProcessHeap();
  v4 = HeapAlloc(ProcessHeap, 0, v1 + 2);
  v5 = v4;
  if ( v4 )
  {
    v6 = (v1 + 2) >> 1;
    if ( v6 )
    {
      v7 = v1 >> 1;
      v8 = (_WORD *)(a1 + 10);
      do
      {
        if ( !v7 )
          break;
        if ( !*v8 )
          break;
        *v4++ = *v8++;
        --v7;
        --v6;
      }
      while ( v6 );
      v9 = v4 - 1;
      if ( v6 )
        v9 = v4;
      *v9 = 0;
    }
    DevGetObjectProperties(3, v5, 4);
    v10 = GetProcessHeap();
    LODWORD(v4) = HeapFree(v10, 0, v5);
  }
  return (int)v4;
}

```

## disassembly

```asm
0x180002038  mov     [rsp-8+arg_10], rbx
0x18000203d  mov     [rsp-8+arg_18], rsi
0x180002042  push    rbp
0x180002043  push    rdi
0x180002044  push    r12
0x180002046  push    r14
0x180002048  push    r15
0x18000204a  lea     rbp, [rsp-37h]
0x18000204f  sub     rsp, 0A0h
0x180002056  mov     rax, cs:__security_cookie
0x18000205d  xor     rax, rsp
0x180002060  mov     [rbp+57h+var_30], rax
0x180002064  movzx   edi, word ptr [rcx+8]
0x180002068  xor     r12d, r12d
0x18000206b  mov     r14, rdx
0x18000206e  mov     [rbp+57h+var_80], r12d
0x180002072  mov     rsi, rcx
0x180002075  mov     [rbp+57h+var_78], r12
0x180002079  lea     rbx, [rdi+2]
0x18000207d  call    cs:__imp_GetProcessHeap
0x180002083  mov     r8, rbx; dwBytes
0x180002086  xor     edx, edx; dwFlags
0x180002088  mov     rcx, rax; hHeap
0x18000208b  call    cs:__imp_HeapAlloc
0x180002091  mov     r15, rax
0x180002094  test    rax, rax
0x180002097  jz      loc_180002299
0x18000209d  shr     rbx, 1
0x1800020a0  jz      short loc_1800020D9
0x1800020a2  shr     rdi, 1
0x1800020a5  lea     rcx, [rsi+0Ah]
0x1800020a9  test    rdi, rdi
0x1800020ac  jz      short loc_1800020CA
0x1800020ae  movzx   edx, word ptr [rcx]
0x1800020b1  test    dx, dx
0x1800020b4  jz      short loc_1800020CA
0x1800020b6  mov     [rax], dx
0x1800020b9  add     rcx, 2
0x1800020bd  add     rax, 2
0x1800020c1  dec     rdi
0x1800020c4  sub     rbx, 1
0x1800020c8  jnz     short loc_1800020A9
0x1800020ca  test    rbx, rbx
0x1800020cd  lea     rcx, [rax-2]
0x1800020d1  cmovnz  rcx, rax
0x1800020d5  mov     [rcx], r12w
0x1800020d9  mov     eax, cs:DEVPKEY_Device_FriendlyName.pid
0x1800020df  mov     r9d, 2
0x1800020e5  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_FriendlyName.fmtid.Data1
0x1800020ec  mov     [rbp+57h+var_60], eax
0x1800020ef  mov     rdx, r15
0x1800020f2  mov     eax, cs:DEVPKEY_Device_DeviceDesc.pid
0x1800020f8  mov     [rbp+57h+var_40], eax
0x1800020fb  lea     r8d, [r9+2]
0x1800020ff  lea     rax, [rbp+57h+var_78]
0x180002103  movaps  [rbp+57h+var_70], xmm0
0x180002107  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_DeviceDesc.fmtid.Data1
0x18000210e  mov     [rsp+0C0h+var_90], rax
0x180002113  lea     ecx, [r9+1]
0x180002117  lea     rax, [rbp+57h+var_80]
0x18000211b  mov     [rbp+57h+var_5C], r12
0x18000211f  mov     [rsp+0C0h+var_98], rax
0x180002124  lea     rax, [rbp+57h+var_70]
0x180002128  mov     [rsp+0C0h+var_A0], rax
0x18000212d  mov     [rbp+57h+var_54], r12d
0x180002131  mov     [rbp+57h+var_3C], r12
0x180002135  mov     [rbp+57h+var_34], r12d
0x180002139  movaps  [rbp+57h+var_50], xmm0
0x18000213d  call    cs:__imp_DevGetObjectProperties
0x180002143  test    eax, eax
0x180002145  js      loc_180002285
0x18000214b  mov     rbx, r12
0x18000214e  mov     esi, r12d
0x180002151  cmp     [rbp+57h+var_80], r12d
0x180002155  jbe     loc_180002285
0x18000215b  mov     rcx, qword ptr cs:DEVPKEY_Device_FriendlyName.fmtid.Data4
0x180002162  mov     rdx, qword ptr cs:DEVPKEY_Device_FriendlyName.fmtid.Data1
0x180002169  mov     r8, qword ptr cs:DEVPKEY_Device_DeviceDesc.fmtid.Data4
0x180002170  mov     r9, qword ptr cs:DEVPKEY_Device_DeviceDesc.fmtid.Data1
0x180002177  mov     eax, esi
0x180002179  lea     rdi, [rax+rax*2]
0x18000217d  mov     rax, [rbp+57h+var_78]
0x180002181  add     rdi, rdi
0x180002184  cmp     dword ptr [rax+rdi*8+10h], 0Eh
0x180002189  jnz     short loc_1800021A1
0x18000218b  cmp     [rax+rdi*8], rdx
0x18000218f  jnz     loc_180002255
0x180002195  cmp     [rax+rdi*8+8], rcx
0x18000219a  jz      short loc_1800021CA
0x18000219c  jmp     loc_180002255
0x1800021a1  cmp     dword ptr [rax+rdi*8+10h], 2
0x1800021a6  jnz     loc_180002255
0x1800021ac  cmp     [rax+rdi*8], r9
0x1800021b0  jnz     loc_180002255
0x1800021b6  cmp     [rax+rdi*8+8], r8
0x1800021bb  jnz     loc_180002255
0x1800021c1  test    rbx, rbx
0x1800021c4  jnz     loc_180002255
0x1800021ca  cmp     [rax+rdi*8+24h], r12d
0x1800021cf  jz      loc_180002255
0x1800021d5  test    rbx, rbx
0x1800021d8  jz      short loc_1800021EE
0x1800021da  call    cs:__imp_GetProcessHeap
0x1800021e0  mov     r8, rbx; lpMem
0x1800021e3  xor     edx, edx; dwFlags
0x1800021e5  mov     rcx, rax; hHeap
0x1800021e8  call    cs:__imp_HeapFree
0x1800021ee  mov     rax, [rbp+57h+var_78]
0x1800021f2  mov     ebx, [rax+rdi*8+24h]
0x1800021f6  call    cs:__imp_GetProcessHeap
0x1800021fc  lea     r8, [rbx+2]; dwBytes
0x180002200  xor     edx, edx; dwFlags
0x180002202  mov     rcx, rax; hHeap
0x180002205  call    cs:__imp_HeapAlloc
0x18000220b  mov     rbx, rax
0x18000220e  test    rax, rax
0x180002211  jz      short loc_180002239
0x180002213  mov     rdx, [rbp+57h+var_78]
0x180002217  mov     rcx, rax; void *
0x18000221a  mov     r8d, [rdx+rdi*8+24h]; Size
0x18000221f  mov     rdx, [rdx+rdi*8+28h]; Src
0x180002224  call    memcpy_0
0x180002229  mov     rax, [rbp+57h+var_78]
0x18000222d  mov     ecx, [rax+rdi*8+24h]
0x180002231  shr     rcx, 1
0x180002234  mov     [rbx+rcx*2], r12w
0x180002239  mov     r9, qword ptr cs:DEVPKEY_Device_DeviceDesc.fmtid.Data1
0x180002240  mov     r8, qword ptr cs:DEVPKEY_Device_DeviceDesc.fmtid.Data4
0x180002247  mov     rdx, qword ptr cs:DEVPKEY_Device_FriendlyName.fmtid.Data1
0x18000224e  mov     rcx, qword ptr cs:DEVPKEY_Device_FriendlyName.fmtid.Data4
0x180002255  inc     esi
0x180002257  cmp     esi, [rbp+57h+var_80]
0x18000225a  jb      loc_180002177
0x180002260  test    rbx, rbx
0x180002263  jz      short loc_180002285
0x180002265  lea     rcx, [r14+48h]; DestinationString
0x180002269  mov     dword ptr [r14+44h], 5
0x180002271  mov     rdx, rbx; SourceString
0x180002274  call    cs:__imp_RtlInitUnicodeString
0x18000227a  mov     dword ptr [r14+90h], 1
0x180002285  call    cs:__imp_GetProcessHeap
0x18000228b  mov     r8, r15; lpMem
0x18000228e  xor     edx, edx; dwFlags
0x180002290  mov     rcx, rax; hHeap
0x180002293  call    cs:__imp_HeapFree
0x180002299  mov     rdx, [rbp+57h+var_78]
0x18000229d  test    rdx, rdx
0x1800022a0  jz      short loc_1800022AB
0x1800022a2  mov     ecx, [rbp+57h+var_80]
0x1800022a5  call    cs:__imp_DevFreeObjectProperties
0x1800022ab  mov     rcx, [rbp+57h+var_30]
0x1800022af  xor     rcx, rsp; StackCookie
0x1800022b2  call    __security_check_cookie
0x1800022b7  lea     r11, [rsp+0C0h+var_20]
0x1800022bf  mov     rbx, [r11+40h]
0x1800022c3  mov     rsi, [r11+48h]
0x1800022c7  mov     rsp, r11
0x1800022ca  pop     r15
0x1800022cc  pop     r14
0x1800022ce  pop     r12
0x1800022d0  pop     rdi
0x1800022d1  pop     rbp
0x1800022d2  retn
```
