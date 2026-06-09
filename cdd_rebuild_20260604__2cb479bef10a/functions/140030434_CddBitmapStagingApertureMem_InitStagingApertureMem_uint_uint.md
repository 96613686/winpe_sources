# CddBitmapStagingApertureMem::InitStagingApertureMem(uint,uint)

- ea: `0x140030434`
- end: `0x1400308c5`
- name: `?InitStagingApertureMem@CddBitmapStagingApertureMem@@QEAAJII@Z`
- size: `1169`
- prototype: `__int64 __fastcall(CddBitmapStagingApertureMem *__hidden this, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400308cc`
- `0x140030dc0`

## callees

- `0x14001b448`
- `0x14002e810`
- `0x140030434`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x1400307fb`
- `ntoskrnl!IoAllocateMdl` at `0x1400307fb`
- `ntoskrnl!DbgPrint` at `0x140030793`
- `ntoskrnl!DbgPrint` at `0x140030793`
- `ntoskrnl!KdDebuggerEnabled` at `0x140030780`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x140030830`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x140030830`
- `watchdog!WdLogSingleEntry1` at `0x140030559`
- `watchdog!WdLogSingleEntry1` at `0x1400305f3`
- `watchdog!WdLogSingleEntry1` at `0x140030632`
- `watchdog!WdLogSingleEntry1` at `0x14003065c`
- `watchdog!WdLogSingleEntry1` at `0x14003069e`
- `watchdog!WdLogSingleEntry1` at `0x1400306d9`
- `watchdog!WdLogSingleEntry1` at `0x140030819`
- `watchdog!WdLogSingleEntry1` at `0x140030559`
- `watchdog!WdLogSingleEntry1` at `0x1400305f3`
- `watchdog!WdLogSingleEntry1` at `0x140030632`
- `watchdog!WdLogSingleEntry1` at `0x14003065c`
- `watchdog!WdLogSingleEntry1` at `0x14003069e`
- `watchdog!WdLogSingleEntry1` at `0x1400306d9`
- `watchdog!WdLogSingleEntry1` at `0x140030819`
- `watchdog!WdLogNewEntry5_WdError` at `0x14003060a`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400307b8`
- `watchdog!WdLogNewEntry5_WdError` at `0x14003087e`
- `watchdog!WdLogNewEntry5_WdError` at `0x14003060a`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400307b8`
- `watchdog!WdLogNewEntry5_WdError` at `0x14003087e`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400305ab`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140030722`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400305ab`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140030722`
- `watchdog!WdLogSingleEntry0` at `0x140030594`
- `watchdog!WdLogSingleEntry0` at `0x14003070b`
- `watchdog!WdLogSingleEntry0` at `0x1400307a1`
- `watchdog!WdLogSingleEntry0` at `0x140030867`
- `watchdog!WdLogSingleEntry0` at `0x140030594`
- `watchdog!WdLogSingleEntry0` at `0x14003070b`
- `watchdog!WdLogSingleEntry0` at `0x1400307a1`
- `watchdog!WdLogSingleEntry0` at `0x140030867`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140030570`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x1400306f0`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140030570`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x1400306f0`

## string_xrefs

- `0x14003078c`: `The staging surface start address must be cache line aligned`

## pseudocode

```c
__int64 __fastcall CddBitmapStagingApertureMem::InitStagingApertureMem(
        CddBitmapStagingApertureMem *this,
        unsigned int a2,
        unsigned int a3)
{
  __int64 v3; // rax
  unsigned int v5; // edx
  _DWORD *v6; // r15
  unsigned int *v7; // r12
  __int64 v8; // rcx
  __int64 v9; // r9
  __int64 v10; // r8
  int v11; // eax
  int v12; // edi
  int v13; // ebx
  _QWORD *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  _QWORD *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  PVOID *v21; // r14
  __int64 v22; // rdx
  __int64 v23; // rcx
  _QWORD *v24; // rax
  unsigned __int64 v25; // rax
  int v26; // ecx
  __int64 v27; // rdx
  __int64 v28; // rcx
  _QWORD *v29; // rax
  __int64 v30; // rdx
  PMDL Mdl; // rax
  __int64 result; // rax
  __int64 v33; // rdx
  __int64 v34; // rcx
  _QWORD *v35; // rax
  int v36; // [rsp+30h] [rbp-78h]
  char v37; // [rsp+58h] [rbp-50h]
  int v38; // [rsp+B8h] [rbp+10h] BYREF

  v3 = *((_QWORD *)this + 1);
  if ( a2 > *(_DWORD *)(v3 + 2472) || a3 > *(_DWORD *)(v3 + 2476) )
  {
    WdLogSingleEntry0(2);
    v13 = 2258;
    WdLogGlobalForLineNumber = 2258;
    v35 = (_QWORD *)WdLogNewEntry5_WdError(v34, v33);
    v35[3] = gCddImageInfo;
    v35[4] = (unsigned int)dword_14003E570;
    v35[5] = 215857758;
    result = 3221225473LL;
    goto LABEL_37;
  }
  *((_DWORD *)this + 4) = a2;
  *((_DWORD *)this + 5) = a3;
  *((_DWORD *)this + 7) = 6;
  *((_DWORD *)this + 8) = 1;
  *((_DWORD *)this + 36) = 0;
  *((_DWORD *)this + 42) = 0;
  *((_DWORD *)this + 9) = 2;
  if ( *(_BYTE *)(v3 + 2751) )
  {
    v5 = (*(_DWORD *)(*((_QWORD *)this + 1) + 7280LL) >> 2)
       & ((*(_DWORD *)(*((_QWORD *)this + 1) + 7272LL) + 4 * a2) >> 2);
    *((_DWORD *)this + 4) = v5;
  }
  else
  {
    v5 = *((_DWORD *)this + 4);
  }
  if ( (*((_DWORD *)this + 43) & 2) != 0 )
    *((_DWORD *)this + 4) = ~g_CPUCacheLineMaskPixels & (v5 + g_CPUCacheLineMaskPixels);
  *((_BYTE *)this + 56) = 0;
  *((_QWORD *)this + 8) = 0;
  v6 = (_DWORD *)((char *)this + 24);
  *((_QWORD *)this + 9) = 0;
  v7 = (unsigned int *)((char *)this + 40);
  v37 = 0;
  *((_WORD *)this + 22) = 0;
  v8 = *((_QWORD *)this + 1);
  v9 = *((unsigned int *)this + 5);
  v10 = *((unsigned int *)this + 4);
  v36 = *((_DWORD *)this + 43);
  v38 = 0;
  v11 = CDDPDEV::CreateAllocation(
          v8,
          0,
          v10,
          v9,
          2,
          *(_DWORD *)(v8 + 1032),
          v36,
          (char *)this + 40,
          &v38,
          0,
          (char *)this + 24,
          v37);
  v12 = v11;
  if ( v11 >= 0 )
  {
    if ( !*v7 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 2313;
      v17 = (_QWORD *)WdLogNewEntry5_WdAssertion(v16, v15);
      v17[3] = gCddImageInfo;
      v17[4] = (unsigned int)dword_14003E570;
      v17[5] = 215857758;
      WdLogGlobalForLineNumber = 2313;
    }
    if ( !*(_BYTE *)(*((_QWORD *)this + 1) + 2751LL) || *v6 == 4 * *((_DWORD *)this + 4) )
    {
      v20 = (unsigned int)*v6;
      if ( (unsigned int)v20 >= 4 * *((_DWORD *)this + 4) )
      {
        if ( (unsigned __int64)*((unsigned int *)this + 5) * v20 <= 0x7FFFFFFF )
        {
          if ( (*((_DWORD *)this + 43) & 2) == 0
            || *(_BYTE *)(*((_QWORD *)this + 1) + 2751LL)
            || !(*v6 % g_CPUCacheLineSizeInBytes) )
          {
            v21 = (PVOID *)((char *)this + 128);
            v12 = CDDPDEV::LockAllocation(*((CDDPDEV **)this + 1), *v7, (unsigned __int8 **)this + 16);
            if ( v12 >= 0 )
            {
              if ( !*v21 )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 2361;
                v24 = (_QWORD *)WdLogNewEntry5_WdAssertion(v23, v22);
                v24[3] = gCddImageInfo;
                v24[4] = (unsigned int)dword_14003E570;
                v24[5] = 215857758;
                WdLogGlobalForLineNumber = 2361;
              }
              v25 = (unsigned __int64)*v21;
              v26 = *((_DWORD *)this + 43);
              *((_QWORD *)this + 17) = (char *)*v21 + (unsigned int)(*v6 * *((_DWORD *)this + 5));
              if ( (v26 & 2) == 0 )
                return 0;
              if ( v25 % g_CPUCacheLineSizeInBytes )
              {
                if ( (_BYTE)KdDebuggerEnabled )
                {
                  DbgPrint("The staging surface start address must be cache line aligned");
                  WdLogSingleEntry0(2);
                  WdLogGlobalForLineNumber = 2371;
                  v29 = (_QWORD *)WdLogNewEntry5_WdError(v28, v27);
                  v30 = (unsigned int)dword_14003E570;
                  v29[3] = gCddImageInfo;
                  v29[4] = v30;
                  v29[5] = 215857758;
                  WdLogGlobalForLineNumber = 2371;
                  __debugbreak();
                }
              }
              Mdl = IoAllocateMdl(*v21, *((_DWORD *)this + 34) - *(_DWORD *)v21, 0, 0, 0);
              *((_QWORD *)this + 22) = Mdl;
              if ( Mdl )
                return 0;
              WdLogSingleEntry1(6, 2);
              v13 = 2380;
              WdLogGlobalForLineNumber = 2380;
              v14 = (_QWORD *)WdLogNewEntry5_WdLowResource();
              v12 = -1073741801;
            }
            else
            {
              WdLogSingleEntry1(4, 2);
              v13 = 2357;
              WdLogGlobalForLineNumber = 2357;
              v14 = (_QWORD *)WdLogNewEntry5_WdEvent();
            }
            goto LABEL_34;
          }
          WdLogSingleEntry1(2, 4);
          v13 = 2345;
        }
        else
        {
          WdLogSingleEntry1(2, 3);
          v13 = 2331;
        }
      }
      else
      {
        WdLogSingleEntry1(2, 2);
        v13 = 2324;
      }
    }
    else
    {
      WdLogSingleEntry1(2, 0);
      v13 = 2317;
    }
    WdLogGlobalForLineNumber = v13;
    v14 = (_QWORD *)WdLogNewEntry5_WdError(v19, v18);
    v12 = -1073741823;
  }
  else
  {
    WdLogSingleEntry1(4, v11);
    v13 = 2309;
    WdLogGlobalForLineNumber = 2309;
    v14 = (_QWORD *)WdLogNewEntry5_WdEvent();
  }
LABEL_34:
  v14[3] = gCddImageInfo;
  v14[4] = (unsigned int)dword_14003E570;
  v14[5] = 215857758;
  result = (unsigned int)v12;
LABEL_37:
  WdLogGlobalForLineNumber = v13;
  return result;
}

```

## disassembly

```asm
0x140030434  push    rbx
0x140030436  push    rbp
0x140030437  push    rsi
0x140030438  push    rdi
0x140030439  push    r12
0x14003043b  push    r13
0x14003043d  push    r14
0x14003043f  push    r15
0x140030441  sub     rsp, 68h
0x140030445  mov     rax, [rcx+8]
0x140030449  mov     rbx, rcx
0x14003044c  cmp     edx, [rax+9A8h]
0x140030452  ja      loc_140030862
0x140030458  cmp     r8d, [rax+9ACh]
0x14003045f  ja      loc_140030862
0x140030465  xor     r13d, r13d
0x140030468  mov     [rcx+10h], edx
0x14003046b  mov     r14d, 1
0x140030471  mov     [rcx+14h], r8d
0x140030475  mov     dword ptr [rcx+1Ch], 6
0x14003047c  mov     [rcx+20h], r14d
0x140030480  mov     [rcx+90h], r13d
0x140030487  lea     esi, [r14+1]
0x14003048b  mov     [rcx+0A8h], r13d
0x140030492  mov     [rcx+24h], esi
0x140030495  mov     al, [rax+0ABFh]
0x14003049b  test    al, al
0x14003049d  jz      short loc_1400304BF
0x14003049f  mov     rcx, [rcx+8]
0x1400304a3  mov     eax, [rcx+1C68h]
0x1400304a9  lea     edx, [rax+rdx*4]
0x1400304ac  mov     eax, [rcx+1C70h]
0x1400304b2  shr     eax, 2
0x1400304b5  shr     edx, 2
0x1400304b8  and     edx, eax
0x1400304ba  mov     [rbx+10h], edx
0x1400304bd  jmp     short loc_1400304C2
0x1400304bf  mov     edx, [rcx+10h]
0x1400304c2  mov     eax, [rbx+0ACh]
0x1400304c8  test    sil, al
0x1400304cb  jz      short loc_1400304DD
0x1400304cd  mov     eax, cs:?g_CPUCacheLineMaskPixels@@3IA; uint g_CPUCacheLineMaskPixels
0x1400304d3  lea     ecx, [rdx+rax]
0x1400304d6  not     eax
0x1400304d8  and     ecx, eax
0x1400304da  mov     [rbx+10h], ecx
0x1400304dd  mov     [rbx+38h], r13b
0x1400304e1  lea     rax, [rsp+0A8h+arg_8]
0x1400304e9  mov     [rbx+40h], r13
0x1400304ed  lea     r15, [rbx+18h]
0x1400304f1  mov     [rbx+48h], r13
0x1400304f5  lea     r12, [rbx+28h]
0x1400304f9  mov     [rsp+0A8h+var_50], r13b
0x1400304fe  xor     edx, edx
0x140030500  mov     [rbx+2Ch], r13w
0x140030505  mov     rcx, [rbx+8]
0x140030509  mov     r9d, [rbx+14h]
0x14003050d  mov     r8d, [rbx+10h]
0x140030511  mov     [rsp+0A8h+var_58], r15
0x140030516  mov     [rsp+0A8h+var_60], r13
0x14003051b  mov     [rsp+0A8h+var_68], rax
0x140030520  mov     eax, [rbx+0ACh]
0x140030526  mov     [rsp+0A8h+var_70], r12
0x14003052b  mov     [rsp+0A8h+var_78], eax
0x14003052f  mov     [rsp+0A8h+arg_8], r13d
0x140030537  mov     eax, [rcx+408h]
0x14003053d  mov     [rsp+0A8h+var_80], eax
0x140030541  mov     dword ptr [rsp+0A8h+Irp], esi
0x140030545  call    ?CreateAllocation@CDDPDEV@@QEAAJPEAVCddBitmap@@IIW4_D3DKMDT_GDISURFACETYPE@@W4_D3DDDIFORMAT@@U_DXGKCDD_CREATE_ALLOCATION_FLAGS@@PEAI4PEAPEAX4E@Z; CDDPDEV::CreateAllocation(CddBitmap *,uint,uint,_D3DKMDT_GDISURFACETYPE,_D3DDDIFORMAT,_DXGKCDD_CREATE_ALLOCATION_FLAGS,uint *,uint *,void * *,uint *,uchar)
0x14003054a  movsxd  rdi, eax
0x14003054d  test    eax, eax
0x14003054f  jns     short loc_140030586
0x140030551  mov     rdx, rdi
0x140030554  mov     ecx, 4
0x140030559  call    cs:__imp_WdLogSingleEntry1
0x140030560  nop     dword ptr [rax+rax+00h]
0x140030565  mov     ebx, 905h
0x14003056a  mov     cs:WdLogGlobalForLineNumber, ebx
0x140030570  call    cs:__imp_WdLogNewEntry5_WdEvent
0x140030577  nop     dword ptr [rax+rax+00h]
0x14003057c  mov     ebp, 0CDDBA5Eh
0x140030581  jmp     loc_140030841
0x140030586  mov     ebp, 0CDDBA5Eh
0x14003058b  cmp     [r12], r13d
0x14003058f  jnz     short loc_1400305D6
0x140030591  mov     ecx, r14d
0x140030594  call    cs:__imp_WdLogSingleEntry0
0x14003059b  nop     dword ptr [rax+rax+00h]
0x1400305a0  mov     edi, 909h
0x1400305a5  mov     cs:WdLogGlobalForLineNumber, edi
0x1400305ab  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x1400305b2  nop     dword ptr [rax+rax+00h]
0x1400305b7  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400305be  mov     [rax+18h], rcx
0x1400305c2  mov     ecx, cs:dword_14003E570
0x1400305c8  mov     [rax+20h], rcx
0x1400305cc  mov     [rax+28h], rbp
0x1400305d0  mov     cs:WdLogGlobalForLineNumber, edi
0x1400305d6  mov     rax, [rbx+8]
0x1400305da  mov     dl, [rax+0ABFh]
0x1400305e0  test    dl, dl
0x1400305e2  jz      short loc_140030620
0x1400305e4  mov     eax, [rbx+10h]
0x1400305e7  shl     eax, 2
0x1400305ea  cmp     [r15], eax
0x1400305ed  jz      short loc_140030620
0x1400305ef  xor     edx, edx
0x1400305f1  mov     ecx, esi
0x1400305f3  call    cs:__imp_WdLogSingleEntry1
0x1400305fa  nop     dword ptr [rax+rax+00h]
0x1400305ff  mov     ebx, 90Dh
0x140030604  mov     cs:WdLogGlobalForLineNumber, ebx
0x14003060a  call    cs:__imp_WdLogNewEntry5_WdError
0x140030611  nop     dword ptr [rax+rax+00h]
0x140030616  mov     edi, 0C0000001h
0x14003061b  jmp     loc_140030841
0x140030620  mov     eax, [rbx+10h]
0x140030623  mov     ecx, [r15]
0x140030626  shl     eax, 2
0x140030629  cmp     ecx, eax
0x14003062b  jnb     short loc_140030645
0x14003062d  mov     rdx, rsi
0x140030630  mov     ecx, esi
0x140030632  call    cs:__imp_WdLogSingleEntry1
0x140030639  nop     dword ptr [rax+rax+00h]
0x14003063e  mov     ebx, 914h
0x140030643  jmp     short loc_140030604
0x140030645  mov     eax, [rbx+14h]
0x140030648  imul    rcx, rax
0x14003064c  cmp     rcx, 7FFFFFFFh
0x140030653  jbe     short loc_14003066F
0x140030655  mov     edx, 3
0x14003065a  mov     ecx, esi
0x14003065c  call    cs:__imp_WdLogSingleEntry1
0x140030663  nop     dword ptr [rax+rax+00h]
0x140030668  mov     ebx, 91Bh
0x14003066d  jmp     short loc_140030604
0x14003066f  mov     eax, [rbx+0ACh]
0x140030675  test    sil, al
0x140030678  jz      short loc_1400306B4
0x14003067a  mov     rax, [rbx+8]
0x14003067e  mov     cl, [rax+0ABFh]
0x140030684  test    cl, cl
0x140030686  jnz     short loc_1400306B4
0x140030688  mov     eax, [r15]
0x14003068b  xor     edx, edx
0x14003068d  div     cs:?g_CPUCacheLineSizeInBytes@@3IA; uint g_CPUCacheLineSizeInBytes
0x140030693  test    edx, edx
0x140030695  jz      short loc_1400306B4
0x140030697  mov     edx, 4
0x14003069c  mov     ecx, esi
0x14003069e  call    cs:__imp_WdLogSingleEntry1
0x1400306a5  nop     dword ptr [rax+rax+00h]
0x1400306aa  mov     ebx, 929h
0x1400306af  jmp     loc_140030604
0x1400306b4  mov     edx, [r12]; unsigned int
0x1400306b8  lea     r14, [rbx+80h]
0x1400306bf  mov     rcx, [rbx+8]; this
0x1400306c3  mov     r8, r14; unsigned __int8 **
0x1400306c6  call    ?LockAllocation@CDDPDEV@@QEAAJIPEAPEAE@Z; CDDPDEV::LockAllocation(uint,uchar * *)
0x1400306cb  mov     edi, eax
0x1400306cd  test    eax, eax
0x1400306cf  jns     short loc_140030701
0x1400306d1  mov     rdx, rsi
0x1400306d4  mov     ecx, 4
0x1400306d9  call    cs:__imp_WdLogSingleEntry1
0x1400306e0  nop     dword ptr [rax+rax+00h]
0x1400306e5  mov     ebx, 935h
0x1400306ea  mov     cs:WdLogGlobalForLineNumber, ebx
0x1400306f0  call    cs:__imp_WdLogNewEntry5_WdEvent
0x1400306f7  nop     dword ptr [rax+rax+00h]
0x1400306fc  jmp     loc_140030841
0x140030701  cmp     [r14], r13
0x140030704  jnz     short loc_14003074D
0x140030706  mov     ecx, 1
0x14003070b  call    cs:__imp_WdLogSingleEntry0
0x140030712  nop     dword ptr [rax+rax+00h]
0x140030717  mov     edi, 939h
0x14003071c  mov     cs:WdLogGlobalForLineNumber, edi
0x140030722  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140030729  nop     dword ptr [rax+rax+00h]
0x14003072e  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140030735  mov     [rax+18h], rcx
0x140030739  mov     ecx, cs:dword_14003E570
0x14003073f  mov     [rax+20h], rcx
0x140030743  mov     [rax+28h], rbp
0x140030747  mov     cs:WdLogGlobalForLineNumber, edi
0x14003074d  mov     edx, [rbx+14h]
0x140030750  imul    edx, [r15]
0x140030754  mov     rax, [r14]
0x140030757  mov     ecx, [rbx+0ACh]
0x14003075d  add     rdx, rax
0x140030760  mov     [rbx+88h], rdx
0x140030767  test    sil, cl
0x14003076a  jz      loc_14003085E
0x140030770  mov     ecx, cs:?g_CPUCacheLineSizeInBytes@@3IA; uint g_CPUCacheLineSizeInBytes
0x140030776  xor     edx, edx
0x140030778  div     rcx
0x14003077b  test    rdx, rdx
0x14003077e  jz      short loc_1400307E4
0x140030780  mov     rax, cs:KdDebuggerEnabled
0x140030787  cmp     [rax], r13b
0x14003078a  jz      short loc_1400307E4
0x14003078c  lea     rcx, aTheStagingSurf; "The staging surface start address must "...
0x140030793  call    cs:__imp_DbgPrint
0x14003079a  nop     dword ptr [rax+rax+00h]
0x14003079f  mov     ecx, esi
0x1400307a1  call    cs:__imp_WdLogSingleEntry0
0x1400307a8  nop     dword ptr [rax+rax+00h]
0x1400307ad  mov     edi, 943h
0x1400307b2  mov     cs:WdLogGlobalForLineNumber, edi
0x1400307b8  call    cs:__imp_WdLogNewEntry5_WdError
0x1400307bf  nop     dword ptr [rax+rax+00h]
0x1400307c4  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400307cb  mov     edx, cs:dword_14003E570
0x1400307d1  mov     [rax+18h], rcx
0x1400307d5  mov     [rax+20h], rdx
0x1400307d9  mov     [rax+28h], rbp
0x1400307dd  mov     cs:WdLogGlobalForLineNumber, edi
0x1400307e3  int     3; Trap to Debugger
0x1400307e4  mov     edx, [rbx+88h]
0x1400307ea  xor     r9d, r9d; ChargeQuota
0x1400307ed  sub     edx, [r14]; Length
0x1400307f0  xor     r8d, r8d; SecondaryBuffer
0x1400307f3  mov     rcx, [r14]; VirtualAddress
0x1400307f6  mov     [rsp+0A8h+Irp], r13; Irp
0x1400307fb  call    cs:__imp_IoAllocateMdl
0x140030802  nop     dword ptr [rax+rax+00h]
0x140030807  mov     [rbx+0B0h], rax
0x14003080e  test    rax, rax
0x140030811  jnz     short loc_14003085E
0x140030813  mov     rdx, rsi
0x140030816  lea     ecx, [rax+6]
0x140030819  call    cs:__imp_WdLogSingleEntry1
0x140030820  nop     dword ptr [rax+rax+00h]
0x140030825  mov     ebx, 94Ch
0x14003082a  mov     cs:WdLogGlobalForLineNumber, ebx
0x140030830  call    cs:__imp_WdLogNewEntry5_WdLowResource
0x140030837  nop     dword ptr [rax+rax+00h]
0x14003083c  mov     edi, 0C0000017h
0x140030841  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140030848  mov     [rax+18h], rcx
0x14003084c  mov     ecx, cs:dword_14003E570
0x140030852  mov     [rax+20h], rcx
0x140030856  mov     [rax+28h], rbp
0x14003085a  mov     eax, edi
0x14003085c  jmp     short loc_1400308AD
0x14003085e  xor     eax, eax
0x140030860  jmp     short loc_1400308B3
0x140030862  mov     ecx, 2
0x140030867  call    cs:__imp_WdLogSingleEntry0
0x14003086e  nop     dword ptr [rax+rax+00h]
0x140030873  mov     ebx, 8D2h
0x140030878  mov     cs:WdLogGlobalForLineNumber, ebx
0x14003087e  call    cs:__imp_WdLogNewEntry5_WdError
0x140030885  nop     dword ptr [rax+rax+00h]
0x14003088a  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140030891  mov     ebp, 0CDDBA5Eh
0x140030896  mov     [rax+18h], rcx
0x14003089a  mov     ecx, cs:dword_14003E570
0x1400308a0  mov     [rax+20h], rcx
0x1400308a4  mov     [rax+28h], rbp
0x1400308a8  mov     eax, 0C0000001h
0x1400308ad  mov     cs:WdLogGlobalForLineNumber, ebx
0x1400308b3  add     rsp, 68h
0x1400308b7  pop     r15
0x1400308b9  pop     r14
0x1400308bb  pop     r13
0x1400308bd  pop     r12
0x1400308bf  pop     rdi
0x1400308c0  pop     rsi
0x1400308c1  pop     rbp
0x1400308c2  pop     rbx
0x1400308c3  retn
```
