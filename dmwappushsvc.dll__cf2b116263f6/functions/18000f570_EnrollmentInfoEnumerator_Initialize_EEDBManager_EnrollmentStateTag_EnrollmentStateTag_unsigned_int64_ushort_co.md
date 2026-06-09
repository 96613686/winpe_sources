# EnrollmentInfoEnumerator::Initialize(EEDBManager *,EnrollmentStateTag,EnrollmentStateTag,unsigned __int64,ushort const *,int,int)

- ea: `0x18000f570`
- end: `0x18000f5fb`
- name: `?Initialize@EnrollmentInfoEnumerator@@QEAAJPEAVEEDBManager@@W4EnrollmentStateTag@@1_KPEBGHH@Z`
- size: `139`
- prototype: `__int64 __fastcall(__int64, __int64, int, int, __int64, __int64, int, int)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e410`
- `0x18000e4e0`
- `0x18000e5b0`
- `0x18000e674`
- `0x18000e750`
- `0x18000e860`

## callees

- `0x18000f0ec`
- `0x18000f570`

## pseudocode

```c
__int64 __fastcall EnrollmentInfoEnumerator::Initialize(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        __int64 a5,
        __int64 a6,
        int a7,
        int a8)
{
  __int64 result; // rax
  __int64 v10; // [rsp+28h] [rbp-40h]
  __int64 v11; // [rsp+30h] [rbp-38h]
  int v12; // [rsp+38h] [rbp-30h]
  int v13; // [rsp+40h] [rbp-28h]
  _QWORD v14[3]; // [rsp+50h] [rbp-18h] BYREF
  DWORD v15; // [rsp+78h] [rbp+10h] BYREF

  v15 = 0;
  v14[0] = 0;
  if ( !a2 )
    return 2147942487LL;
  v13 = a8;
  v12 = a7;
  v11 = a6;
  v10 = a5;
  *(_QWORD *)(a1 + 24) = a2;
  result = EnrollmentInfoEnumerator::GetAllEnrollmentIDsFiltered(a1, &v15, v14, a3, a4, v10, v11, v12, v13);
  if ( (int)result >= 0 )
  {
    *(_DWORD *)(a1 + 40) = v15;
    *(_QWORD *)(a1 + 48) = v14[0];
  }
  return result;
}

```

## disassembly

```asm
0x18000f570  push    rbx
0x18000f572  sub     rsp, 60h
0x18000f576  mov     [rsp+68h+arg_8], 0
0x18000f57e  mov     rbx, rcx
0x18000f581  mov     [rsp+68h+var_18], 0
0x18000f58a  test    rdx, rdx
0x18000f58d  jnz     short loc_18000F596
0x18000f58f  mov     eax, 80070057h
0x18000f594  jmp     short loc_18000F5F5
0x18000f596  mov     eax, [rsp+68h+arg_38]
0x18000f59d  mov     [rsp+68h+var_28], eax
0x18000f5a1  mov     eax, [rsp+68h+arg_30]
0x18000f5a8  mov     [rsp+68h+var_30], eax
0x18000f5ac  mov     rax, [rsp+68h+arg_28]
0x18000f5b4  mov     [rsp+68h+var_38], rax
0x18000f5b9  mov     rax, [rsp+68h+arg_20]
0x18000f5c1  mov     [rsp+68h+var_40], rax
0x18000f5c6  mov     [rsp+68h+var_48], r9d
0x18000f5cb  mov     r9d, r8d
0x18000f5ce  mov     [rcx+18h], rdx
0x18000f5d2  lea     r8, [rsp+68h+var_18]
0x18000f5d7  lea     rdx, [rsp+68h+arg_8]
0x18000f5dc  call    ?GetAllEnrollmentIDsFiltered@EnrollmentInfoEnumerator@@AEAAJPEAKPEAPEAPEAGW4EnrollmentStateTag@@2_KPEBGHH@Z; EnrollmentInfoEnumerator::GetAllEnrollmentIDsFiltered(ulong *,ushort * * *,EnrollmentStateTag,EnrollmentStateTag,unsigned __int64,ushort const *,int,int)
0x18000f5e1  test    eax, eax
0x18000f5e3  js      short loc_18000F5F5
0x18000f5e5  mov     ecx, [rsp+68h+arg_8]
0x18000f5e9  mov     [rbx+28h], ecx
0x18000f5ec  mov     rcx, [rsp+68h+var_18]
0x18000f5f1  mov     [rbx+30h], rcx
0x18000f5f5  add     rsp, 60h
0x18000f5f9  pop     rbx
0x18000f5fa  retn
```
