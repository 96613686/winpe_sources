# WSTDereferenceUserModeContext(_NEGOEXTS_UMODE_CONTEXT *)

- ea: `0x180018ea0`
- end: `0x180018f22`
- name: `?WSTDereferenceUserModeContext@@YAXPEAU_NEGOEXTS_UMODE_CONTEXT@@@Z`
- size: `130`
- prototype: `void __fastcall(struct _NEGOEXTS_UMODE_CONTEXT *)`
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000c5a4`
- `0x18000c5f0`
- `0x18000d234`
- `0x180018f28`
- `0x180019124`
- `0x180019200`
- `0x180019840`
- `0x180019950`
- `0x180019a70`
- `0x180019bf0`

## callees

- `0x180018ea0`
- `0x180019080`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180018f00`
- `ntdll!RtlLeaveCriticalSection` at `0x180018f00`
- `ntdll!RtlEnterCriticalSection` at `0x180018ef1`
- `ntdll!RtlEnterCriticalSection` at `0x180018ef1`

## pseudocode

```c
void __fastcall WSTDereferenceUserModeContext(struct _NEGOEXTS_UMODE_CONTEXT *a1)
{
  unsigned int v1; // r8d
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  int v4; // ebx

  v1 = *((_DWORD *)a1 + 8);
  v3 = (struct _RTL_CRITICAL_SECTION *)&qword_180027D40[7
                                                      * (unsigned __int8)((v1 >> 4)
                                                                        + BYTE2(v1)
                                                                        + HIBYTE(v1)
                                                                        + v1
                                                                        + BYTE1(v1)
                                                                        + (((v1 >> 4)
                                                                          + HIWORD(v1)
                                                                          + HIBYTE(v1)
                                                                          + v1
                                                                          + (v1 >> 8)) >> 4))];
  RtlEnterCriticalSection(v3);
  v4 = --*((_DWORD *)a1 + 4);
  RtlLeaveCriticalSection(v3);
  if ( !v4 )
    WSTFreeUserModeContext(a1);
}

```

## disassembly

```asm
0x180018ea0  mov     [rsp+arg_0], rbx
0x180018ea5  mov     [rsp+arg_8], rsi
0x180018eaa  push    rdi
0x180018eab  sub     rsp, 20h
0x180018eaf  mov     r8d, [rcx+20h]
0x180018eb3  mov     rsi, rcx
0x180018eb6  mov     eax, r8d
0x180018eb9  mov     edx, r8d
0x180018ebc  shr     eax, 10h
0x180018ebf  shr     edx, 18h
0x180018ec2  add     edx, eax
0x180018ec4  mov     eax, r8d
0x180018ec7  shr     eax, 8
0x180018eca  add     eax, r8d
0x180018ecd  shr     r8d, 4
0x180018ed1  add     eax, edx
0x180018ed3  add     eax, r8d
0x180018ed6  mov     ecx, eax
0x180018ed8  shr     ecx, 4
0x180018edb  add     ecx, eax
0x180018edd  movzx   eax, cl
0x180018ee0  imul    rdi, rax, 38h ; '8'
0x180018ee4  lea     rax, qword_180027D40
0x180018eeb  add     rdi, rax
0x180018eee  mov     rcx, rdi; CriticalSection
0x180018ef1  call    cs:__imp_RtlEnterCriticalSection
0x180018ef7  dec     dword ptr [rsi+10h]
0x180018efa  mov     rcx, rdi; CriticalSection
0x180018efd  mov     ebx, [rsi+10h]
0x180018f00  call    cs:__imp_RtlLeaveCriticalSection
0x180018f06  test    ebx, ebx
0x180018f08  jnz     short loc_180018F12
0x180018f0a  mov     rcx, rsi; struct _NEGOEXTS_UMODE_CONTEXT *
0x180018f0d  call    ?WSTFreeUserModeContext@@YAXPEAU_NEGOEXTS_UMODE_CONTEXT@@@Z; WSTFreeUserModeContext(_NEGOEXTS_UMODE_CONTEXT *)
0x180018f12  mov     rbx, [rsp+28h+arg_0]
0x180018f17  mov     rsi, [rsp+28h+arg_8]
0x180018f1c  add     rsp, 20h
0x180018f20  pop     rdi
0x180018f21  retn
```
