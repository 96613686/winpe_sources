# CDetectionAndSharing::GetFWServiceInfo(int *,int *)

- ea: `0x180002e2c`
- end: `0x180002e87`
- name: `?GetFWServiceInfo@CDetectionAndSharing@@AEAAJPEAH0@Z`
- size: `91`
- prototype: `__int64 __fastcall(CDetectionAndSharing *__hidden this, int *, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800025c8`
- `0x180002b64`

## callees

- `0x180002e2c`
- `0x180002fc4`

## pseudocode

```c
__int64 __fastcall CDetectionAndSharing::GetFWServiceInfo(SC_HANDLE *this, int *a2, int *a3)
{
  __int64 result; // rax
  unsigned int v6[6]; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v7; // [rsp+58h] [rbp+20h] BYREF

  v6[0] = 0;
  v7 = 0;
  result = CDetectionAndSharing::GetServiceInfo(this, L"mpssvc", v6, &v7);
  if ( (int)result >= 0 )
  {
    *a2 = v7 == 4;
    *a3 = v6[0] == 4;
  }
  return result;
}

```

## disassembly

```asm
0x180002e2c  mov     rax, rsp
0x180002e2f  mov     [rax+8], rbx
0x180002e33  push    rdi
0x180002e34  sub     rsp, 30h
0x180002e38  mov     rbx, r8
0x180002e3b  mov     dword ptr [rax-18h], 0
0x180002e42  mov     rdi, rdx
0x180002e45  mov     dword ptr [rax+20h], 0
0x180002e4c  lea     r8, [rax-18h]; unsigned int *
0x180002e50  lea     rdx, aMpssvc; "mpssvc"
0x180002e57  lea     r9, [rax+20h]; unsigned int *
0x180002e5b  call    ?GetServiceInfo@CDetectionAndSharing@@AEAAJPEBGPEAK1@Z; CDetectionAndSharing::GetServiceInfo(ushort const *,ulong *,ulong *)
0x180002e60  test    eax, eax
0x180002e62  js      short loc_180002E7C
0x180002e64  xor     ecx, ecx
0x180002e66  cmp     [rsp+38h+arg_18], 4
0x180002e6b  setz    cl
0x180002e6e  mov     [rdi], ecx
0x180002e70  xor     ecx, ecx
0x180002e72  cmp     [rsp+38h+var_18], 4
0x180002e77  setz    cl
0x180002e7a  mov     [rbx], ecx
0x180002e7c  mov     rbx, [rsp+38h+arg_0]
0x180002e81  add     rsp, 30h
0x180002e85  pop     rdi
0x180002e86  retn
```
