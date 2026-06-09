# RUPTelemetryProvider::RupDeploymentMethod<ulong,uint &>(ulong &&,uint &)

- ea: `0x180004250`
- end: `0x180004397`
- name: `??$RupDeploymentMethod@KAEAI@RUPTelemetryProvider@@SAX$$QEAKAEAI@Z`
- size: `327`
- prototype: `__int64 __fastcall(int *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180004660`

## callees

- `0x180004250`
- `0x180004780`
- `0x18000a520`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180004370`
- `ntdll!EtwEventWriteTransfer` at `0x180004370`

## pseudocode

```c
__int64 __fastcall RUPTelemetryProvider::RupDeploymentMethod<unsigned long,unsigned int &>(int *a1, int *a2)
{
  _QWORD *v4; // rcx
  __int64 result; // rax
  __int64 v6; // r8
  int v7; // [rsp+30h] [rbp-78h] BYREF
  int v8; // [rsp+34h] [rbp-74h] BYREF
  __int64 v9; // [rsp+38h] [rbp-70h]
  _DWORD v10[2]; // [rsp+40h] [rbp-68h] BYREF
  __int64 v11; // [rsp+48h] [rbp-60h]
  unsigned __int16 *v12; // [rsp+50h] [rbp-58h] BYREF
  int v13; // [rsp+58h] [rbp-50h]
  int v14; // [rsp+5Ch] [rbp-4Ch]
  void *v15; // [rsp+60h] [rbp-48h]
  __int64 v16; // [rsp+68h] [rbp-40h]
  int *v17; // [rsp+70h] [rbp-38h]
  __int64 v18; // [rsp+78h] [rbp-30h]
  int *v19; // [rsp+80h] [rbp-28h]
  __int64 v20; // [rsp+88h] [rbp-20h]

  v4 = (_QWORD *)*((_QWORD *)RUPTelemetryProvider::Instance() + 1);
  result = *(unsigned int *)v4;
  if ( (unsigned int)result > 5 )
  {
    v6 = v4[3];
    result = v4[2];
    if ( (result & 0x200000000000LL) != 0 )
    {
      result = v6 & 0x200000000000LL;
      if ( (v6 & 0x200000000000LL) == v6 )
      {
        v7 = *a2;
        v8 = *a1;
        v19 = &v7;
        v17 = &v8;
        v10[1] = 5;
        v12 = (unsigned __int16 *)v4[1];
        v11 = 0x200000000000LL;
        v20 = 4;
        v18 = 4;
        v10[0] = 184549376;
        v13 = *v12;
        v15 = &unk_180024FB0;
        v14 = 2;
        v16 = 0x10000003BLL;
        LODWORD(v9) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        return ((__int64 (__fastcall *)(_QWORD, _DWORD *, _QWORD, _QWORD, int, unsigned __int16 **, int, __int64))EtwEventWriteTransfer)(
                 v4[4],
                 v10,
                 0,
                 0,
                 4,
                 &v12,
                 v7,
                 v9);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004250  mov     [rsp+arg_0], rbx
0x180004255  push    rdi
0x180004256  sub     rsp, 0A0h
0x18000425d  mov     rax, cs:__security_cookie
0x180004264  xor     rax, rsp
0x180004267  mov     [rsp+0A8h+var_18], rax
0x18000426f  mov     rbx, rdx
0x180004272  mov     rdi, rcx
0x180004275  call    ?Instance@RUPTelemetryProvider@@KAPEAV1@XZ; RUPTelemetryProvider::Instance(void)
0x18000427a  mov     rcx, [rax+8]
0x18000427e  mov     eax, [rcx]
0x180004280  cmp     eax, 5
0x180004283  jbe     loc_180004376
0x180004289  mov     r8, [rcx+18h]
0x18000428d  mov     r9, 200000000000h
0x180004297  mov     rax, [rcx+10h]
0x18000429b  test    r9, rax
0x18000429e  jz      loc_180004376
0x1800042a4  mov     rax, r8
0x1800042a7  and     rax, r9
0x1800042aa  cmp     rax, r8
0x1800042ad  jnz     loc_180004376
0x1800042b3  mov     eax, [rbx]
0x1800042b5  lea     rdx, _TraceLoggingMetadata
0x1800042bc  mov     [rsp+0A8h+var_78], eax
0x1800042c0  xor     r8d, r8d
0x1800042c3  mov     eax, [rdi]
0x1800042c5  mov     [rsp+0A8h+var_74], eax
0x1800042c9  lea     rax, [rsp+0A8h+var_78]
0x1800042ce  mov     [rsp+0A8h+var_28], rax
0x1800042d6  lea     rax, [rsp+0A8h+var_74]
0x1800042db  mov     [rsp+0A8h+var_38], rax
0x1800042e0  movzx   eax, cs:word_180024FA6
0x1800042e7  mov     [rsp+0A8h+var_64], eax
0x1800042eb  mov     rax, [rcx+8]
0x1800042ef  mov     [rsp+0A8h+var_58], rax
0x1800042f4  mov     [rsp+0A8h+var_60], r9
0x1800042f9  xor     r9d, r9d
0x1800042fc  mov     [rsp+0A8h+var_20], 4
0x180004308  mov     [rsp+0A8h+var_30], 4
0x180004311  mov     [rsp+0A8h+var_68], 0B000000h
0x180004319  movzx   eax, word ptr [rax]
0x18000431c  mov     [rsp+0A8h+var_50], eax
0x180004320  lea     rax, unk_180024FB0
0x180004327  mov     [rsp+0A8h+var_48], rax
0x18000432c  lea     rax, _TraceLoggingMetadataEnd
0x180004333  sub     eax, edx
0x180004335  mov     [rsp+0A8h+var_4C], 2
0x18000433d  mov     dword ptr [rsp+0A8h+var_40], 3Bh ; ';'
0x180004345  lea     rdx, [rsp+0A8h+var_68]
0x18000434a  mov     dword ptr [rsp+0A8h+var_40+4], 1
0x180004352  mov     dword ptr [rsp+0A8h+var_70], eax
0x180004356  mov     eax, dword ptr [rsp+0A8h+var_70]
0x18000435a  mov     rcx, [rcx+20h]
0x18000435e  lea     rax, [rsp+0A8h+var_58]
0x180004363  mov     [rsp+0A8h+var_80], rax
0x180004368  mov     [rsp+0A8h+var_88], 4
0x180004370  call    cs:__imp_EtwEventWriteTransfer
0x180004376  mov     rcx, [rsp+0A8h+var_18]
0x18000437e  xor     rcx, rsp; StackCookie
0x180004381  call    __security_check_cookie
0x180004386  mov     rbx, [rsp+0A8h+arg_0]
0x18000438e  add     rsp, 0A0h
0x180004395  pop     rdi
0x180004396  retn
```
