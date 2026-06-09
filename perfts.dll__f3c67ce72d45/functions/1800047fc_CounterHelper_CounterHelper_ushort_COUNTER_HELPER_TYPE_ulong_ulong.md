# CounterHelper::CounterHelper(ushort *,COUNTER_HELPER_TYPE,ulong,ulong)

- ea: `0x1800047fc`
- end: `0x18000498e`
- name: `??0CounterHelper@@QEAA@PEAGW4COUNTER_HELPER_TYPE@@KK@Z`
- size: `402`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180004e40`
- `0x1800058b8`
- `0x180007668`
- `0x180008074`

## callees

- `0x1800047fc`
- `0x180006598`
- `0x1800098f6`

## pseudocode

```c
__int64 __fastcall CounterHelper::CounterHelper(__int64 a1, unsigned __int16 *a2, int a3, int a4, int a5)
{
  __int64 v7; // rbx
  __int64 v8; // rax
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int64 v19; // rax
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v31; // [rsp+20h] [rbp-91h] BYREF
  __int128 v32; // [rsp+30h] [rbp-81h]
  __int128 v33; // [rsp+40h] [rbp-71h]
  __int128 v34; // [rsp+50h] [rbp-61h]
  __int128 v35; // [rsp+60h] [rbp-51h]
  __int128 v36; // [rsp+70h] [rbp-41h]
  __int128 v37; // [rsp+80h] [rbp-31h]
  __int128 v38; // [rsp+90h] [rbp-21h]
  __int128 v39; // [rsp+A0h] [rbp-11h]
  __int128 v40; // [rsp+B0h] [rbp-1h]
  __int128 v41; // [rsp+C0h] [rbp+Fh]
  __int64 v42; // [rsp+D0h] [rbp+1Fh]

  *(_QWORD *)a1 = 0;
  v7 = a1 + 48;
  *(_QWORD *)(a1 + 8) = 0;
  *(_DWORD *)(a1 + 16) = 1;
  *(_DWORD *)(a1 + 32) = 1;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_DWORD *)(a1 + 416) = a3;
  *(_DWORD *)(a1 + 424) = a5;
  *(_DWORD *)(a1 + 420) = a4;
  if ( a3 == 2 )
  {
    memset_0(&v31, 0, 0xB8u);
    v8 = v42;
    v9 = v32;
    *(_OWORD *)v7 = v31;
    v10 = v33;
    *(_OWORD *)(v7 + 16) = v9;
    v11 = v34;
    *(_OWORD *)(v7 + 32) = v10;
    v12 = v35;
    *(_OWORD *)(v7 + 48) = v11;
    v13 = v36;
    *(_OWORD *)(v7 + 64) = v12;
    v14 = v37;
    *(_OWORD *)(v7 + 80) = v13;
    v15 = v38;
    *(_OWORD *)(v7 + 96) = v14;
    v16 = v39;
    *(_OWORD *)(v7 + 112) = v15;
    v17 = v40;
    *(_OWORD *)(v7 + 128) = v16;
    v18 = v41;
    *(_OWORD *)(v7 + 144) = v17;
    *(_OWORD *)(v7 + 160) = v18;
    *(_QWORD *)(v7 + 176) = v8;
    InitInstance((struct _USER_INPUT_DELAY_INSTANCE *)v7, L"Max");
    memset_0(&v31, 0, 0xB8u);
    v7 = a1 + 232;
    a2 = L"Average";
  }
  else
  {
    memset_0(&v31, 0, 0xB8u);
  }
  v19 = v42;
  v20 = v32;
  *(_OWORD *)v7 = v31;
  v21 = v33;
  *(_OWORD *)(v7 + 16) = v20;
  v22 = v34;
  *(_OWORD *)(v7 + 32) = v21;
  v23 = v35;
  *(_OWORD *)(v7 + 48) = v22;
  v24 = v36;
  *(_OWORD *)(v7 + 64) = v23;
  v25 = v37;
  *(_OWORD *)(v7 + 80) = v24;
  v26 = v38;
  *(_OWORD *)(v7 + 96) = v25;
  v27 = v39;
  *(_OWORD *)(v7 + 112) = v26;
  v28 = v40;
  *(_OWORD *)(v7 + 128) = v27;
  v29 = v41;
  *(_OWORD *)(v7 + 144) = v28;
  *(_OWORD *)(v7 + 160) = v29;
  *(_QWORD *)(v7 + 176) = v19;
  InitInstance((struct _USER_INPUT_DELAY_INSTANCE *)v7, a2);
  return a1;
}

```

## disassembly

```asm
0x1800047fc  push    rbp
0x1800047fe  push    rbx
0x1800047ff  push    rsi
0x180004800  push    rdi
0x180004801  lea     rbp, [rsp-37h]
0x180004806  sub     rsp, 0E8h
0x18000480d  mov     rdi, rcx
0x180004810  mov     rsi, rdx
0x180004813  xor     ecx, ecx
0x180004815  xor     edx, edx; Val
0x180004817  cmp     r8d, 2
0x18000481b  mov     [rdi], rcx
0x18000481e  lea     rbx, [rdi+30h]
0x180004822  lea     eax, [rcx+1]
0x180004825  mov     [rdi+8], rcx
0x180004829  mov     [rdi+10h], eax
0x18000482c  mov     [rdi+20h], eax
0x18000482f  mov     eax, [rbp+4Fh+arg_20]
0x180004832  mov     [rdi+18h], rcx
0x180004836  mov     [rdi+28h], rcx
0x18000483a  lea     rcx, [rsp+100h+var_E0]; void *
0x18000483f  mov     [rdi+1A0h], r8d
0x180004846  mov     r8d, 0B8h; Size
0x18000484c  mov     [rdi+1A8h], eax
0x180004852  mov     [rdi+1A4h], r9d
0x180004859  jnz     loc_180004902
0x18000485f  call    memset_0
0x180004864  movups  xmm0, [rsp+100h+var_E0]
0x180004869  mov     rax, [rbp+4Fh+var_30]
0x18000486d  lea     rdx, aMax; "Max"
0x180004874  movups  xmm1, [rsp+100h+var_D0]
0x180004879  mov     rcx, rbx; struct _USER_INPUT_DELAY_INSTANCE *
0x18000487c  movups  xmmword ptr [rbx], xmm0
0x18000487f  movups  xmm0, [rbp+4Fh+var_C0]
0x180004883  movups  xmmword ptr [rbx+10h], xmm1
0x180004887  movups  xmm1, [rbp+4Fh+var_B0]
0x18000488b  movups  xmmword ptr [rbx+20h], xmm0
0x18000488f  movups  xmm0, [rbp+4Fh+var_A0]
0x180004893  movups  xmmword ptr [rbx+30h], xmm1
0x180004897  movups  xmm1, [rbp+4Fh+var_90]
0x18000489b  movups  xmmword ptr [rbx+40h], xmm0
0x18000489f  movups  xmm0, [rbp+4Fh+var_80]
0x1800048a3  movups  xmmword ptr [rbx+50h], xmm1
0x1800048a7  movups  xmm1, [rbp+4Fh+var_70]
0x1800048ab  movups  xmmword ptr [rbx+60h], xmm0
0x1800048af  movups  xmm0, [rbp+4Fh+var_60]
0x1800048b3  movups  xmmword ptr [rbx+70h], xmm1
0x1800048b7  movups  xmm1, [rbp+4Fh+var_50]
0x1800048bb  movups  xmmword ptr [rbx+80h], xmm0
0x1800048c2  movups  xmm0, [rbp+4Fh+var_40]
0x1800048c6  movups  xmmword ptr [rbx+90h], xmm1
0x1800048cd  movups  xmmword ptr [rbx+0A0h], xmm0
0x1800048d4  mov     [rbx+0B0h], rax
0x1800048db  call    ?InitInstance@@YAXPEAU_USER_INPUT_DELAY_INSTANCE@@PEAG@Z; InitInstance(_USER_INPUT_DELAY_INSTANCE *,ushort *)
0x1800048e0  xor     edx, edx; Val
0x1800048e2  lea     rcx, [rsp+100h+var_E0]; void *
0x1800048e7  mov     r8d, 0B8h; Size
0x1800048ed  call    memset_0
0x1800048f2  lea     rbx, [rdi+0E8h]
0x1800048f9  lea     rsi, aAverage; "Average"
0x180004900  jmp     short loc_180004907
0x180004902  call    memset_0
0x180004907  movups  xmm0, [rsp+100h+var_E0]
0x18000490c  mov     rax, [rbp+4Fh+var_30]
0x180004910  mov     rdx, rsi; unsigned __int16 *
0x180004913  movups  xmm1, [rsp+100h+var_D0]
0x180004918  mov     rcx, rbx; struct _USER_INPUT_DELAY_INSTANCE *
0x18000491b  movups  xmmword ptr [rbx], xmm0
0x18000491e  movups  xmm0, [rbp+4Fh+var_C0]
0x180004922  movups  xmmword ptr [rbx+10h], xmm1
0x180004926  movups  xmm1, [rbp+4Fh+var_B0]
0x18000492a  movups  xmmword ptr [rbx+20h], xmm0
0x18000492e  movups  xmm0, [rbp+4Fh+var_A0]
0x180004932  movups  xmmword ptr [rbx+30h], xmm1
0x180004936  movups  xmm1, [rbp+4Fh+var_90]
0x18000493a  movups  xmmword ptr [rbx+40h], xmm0
0x18000493e  movups  xmm0, [rbp+4Fh+var_80]
0x180004942  movups  xmmword ptr [rbx+50h], xmm1
0x180004946  movups  xmm1, [rbp+4Fh+var_70]
0x18000494a  movups  xmmword ptr [rbx+60h], xmm0
0x18000494e  movups  xmm0, [rbp+4Fh+var_60]
0x180004952  movups  xmmword ptr [rbx+70h], xmm1
0x180004956  movups  xmm1, [rbp+4Fh+var_50]
0x18000495a  movups  xmmword ptr [rbx+80h], xmm0
0x180004961  movups  xmm0, [rbp+4Fh+var_40]
0x180004965  movups  xmmword ptr [rbx+90h], xmm1
0x18000496c  movups  xmmword ptr [rbx+0A0h], xmm0
0x180004973  mov     [rbx+0B0h], rax
0x18000497a  call    ?InitInstance@@YAXPEAU_USER_INPUT_DELAY_INSTANCE@@PEAG@Z; InitInstance(_USER_INPUT_DELAY_INSTANCE *,ushort *)
0x18000497f  mov     rax, rdi
0x180004982  add     rsp, 0E8h
0x180004989  pop     rdi
0x18000498a  pop     rsi
0x18000498b  pop     rbx
0x18000498c  pop     rbp
0x18000498d  retn
```
