# CDDPDEV::EnsureResident(CddResidencyState *,CHwCommandBuffer *,uchar,unsigned __int64 *)

- ea: `0x1400112f0`
- end: `0x1400113cb`
- name: `?EnsureResident@CDDPDEV@@QEAAJPEAVCddResidencyState@@PEAVCHwCommandBuffer@@EPEA_K@Z`
- size: `219`
- prototype: `__int64 __usercall@<rax>(CDDPDEV *__hidden this@<rcx>, struct CddResidencyState *@<rdx>, struct CHwCommandBuffer *@<r8>, unsigned __int8@<r9b>, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140010c2c`

## callees

- `0x1400112f0`
- `0x140015764`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140011334`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140011334`
- `watchdog!WdLogSingleEntry0` at `0x14001131d`
- `watchdog!WdLogSingleEntry0` at `0x14001131d`

## pseudocode

```c
__int64 __fastcall CDDPDEV::EnsureResident(
        CDDPDEV *this,
        struct CddResidencyState *a2,
        struct CHwCommandBuffer *a3,
        __int64 a4,
        unsigned __int64 *a5)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  _QWORD *v10; // rax
  bool v11; // zf
  __int64 result; // rax

  if ( *(struct _KTHREAD **)(*((_QWORD *)this + 1600) + 8LL) != KeGetCurrentThread() )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 680;
    v10 = (_QWORD *)WdLogNewEntry5_WdAssertion(v9, v8);
    v10[3] = gCddImageInfo;
    v10[4] = (unsigned int)dword_14003E570;
    v10[5] = 215857758;
    WdLogGlobalForLineNumber = 680;
  }
  v11 = *((_BYTE *)a2 + 8) == 0;
  *a5 = 0;
  if ( !v11 )
    return *((_QWORD *)a2 + 2) != 0 ? 0x103 : 0;
  result = CDDPDEV::EnsureResident(this, *(_DWORD *)(*(_QWORD *)a2 + 40LL), a3, 0, a5);
  if ( (int)result >= 0 )
  {
    *((_BYTE *)a2 + 8) = 1;
    if ( (_DWORD)result == 259 )
      *((_QWORD *)a2 + 2) = *a5;
    else
      *((_QWORD *)a2 + 2) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400112f0  push    rbx
0x1400112f2  push    rbp
0x1400112f3  push    rsi
0x1400112f4  push    rdi
0x1400112f5  sub     rsp, 38h
0x1400112f9  mov     r9, gs:188h
0x140011302  mov     rbp, r8
0x140011305  mov     rax, [rcx+3200h]
0x14001130c  mov     rbx, rdx
0x14001130f  mov     rsi, rcx
0x140011312  cmp     [rax+8], r9
0x140011316  jz      short loc_140011363
0x140011318  mov     ecx, 1
0x14001131d  call    cs:__imp_WdLogSingleEntry0
0x140011324  nop     dword ptr [rax+rax+00h]
0x140011329  mov     edi, 2A8h
0x14001132e  mov     cs:WdLogGlobalForLineNumber, edi
0x140011334  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14001133b  nop     dword ptr [rax+rax+00h]
0x140011340  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140011347  mov     [rax+18h], rcx
0x14001134b  mov     ecx, cs:dword_14003E570
0x140011351  mov     [rax+20h], rcx
0x140011355  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001135d  mov     cs:WdLogGlobalForLineNumber, edi
0x140011363  cmp     byte ptr [rbx+8], 0
0x140011367  mov     rdi, [rsp+58h+arg_20]
0x14001136f  mov     qword ptr [rdi], 0
0x140011376  jz      short loc_140011390
0x140011378  mov     rax, [rbx+10h]
0x14001137c  neg     rax
0x14001137f  sbb     eax, eax
0x140011381  and     eax, 103h
0x140011386  add     rsp, 38h
0x14001138a  pop     rdi
0x14001138b  pop     rsi
0x14001138c  pop     rbp
0x14001138d  pop     rbx
0x14001138e  retn
0x140011390  mov     rdx, [rbx]
0x140011393  xor     r9d, r9d; unsigned __int8
0x140011396  mov     r8, rbp; struct CHwCommandBuffer *
0x140011399  mov     [rsp+58h+var_38], rdi; unsigned __int64 *
0x14001139e  mov     rcx, rsi; this
0x1400113a1  mov     edx, [rdx+28h]; unsigned int
0x1400113a4  call    ?EnsureResident@CDDPDEV@@QEAAJIPEAVCHwCommandBuffer@@EPEA_K@Z; CDDPDEV::EnsureResident(uint,CHwCommandBuffer *,uchar,unsigned __int64 *)
0x1400113a9  test    eax, eax
0x1400113ab  js      short loc_140011386
0x1400113ad  mov     byte ptr [rbx+8], 1
0x1400113b1  cmp     eax, 103h
0x1400113b6  jnz     short loc_1400113C1
0x1400113b8  mov     rcx, [rdi]
0x1400113bb  mov     [rbx+10h], rcx
0x1400113bf  jmp     short loc_140011386
0x1400113c1  mov     qword ptr [rbx+10h], 0
0x1400113c9  jmp     short loc_140011386
```
