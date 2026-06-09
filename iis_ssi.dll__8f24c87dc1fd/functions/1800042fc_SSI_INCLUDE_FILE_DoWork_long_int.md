# SSI_INCLUDE_FILE::DoWork(long,int *)

- ea: `0x1800042fc`
- end: `0x180004744`
- name: `?DoWork@SSI_INCLUDE_FILE@@QEAAJJPEAH@Z`
- size: `1096`
- prototype: `int __fastcall(SSI_INCLUDE_FILE *this, int, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800034b0`

## callees

- `0x18000395c`
- `0x1800042fc`
- `0x180004afc`
- `0x1800054e4`
- `0x180005548`
- `0x180005780`
- `0x180006010`

## import_xrefs

- `msvcrt!_itoa_s` at `0x1800044c8`
- `msvcrt!_itoa_s` at `0x1800044c8`

## pseudocode

```c
int __fastcall SSI_INCLUDE_FILE::DoWork(SSI_INCLUDE_FILE *this, int a2, int *a3)
{
  int v5; // edi
  int v6; // ecx
  unsigned int v7; // esi
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int result; // eax
  __int64 v13; // rcx
  __int64 v14; // r14
  __int64 v15; // rax
  unsigned int v16; // r10d
  int v17; // ecx
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rax
  __int64 v24; // r9
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rdi
  char *v30; // rax
  int v31; // eax
  void *v32; // rax
  unsigned __int16 v33[2]; // [rsp+60h] [rbp-19h] BYREF
  __int16 v34; // [rsp+64h] [rbp-15h] BYREF
  unsigned int v35[2]; // [rsp+68h] [rbp-11h] BYREF
  char *v36[2]; // [rsp+70h] [rbp-9h] BYREF
  char Buffer[32]; // [rsp+80h] [rbp+7h] BYREF

  *a3 = 0;
  v5 = -2147467259;
  *(_OWORD *)v36 = 0;
  if ( a2 < 0 && *((_DWORD *)this + 171) != 2 )
  {
    *((_DWORD *)this + 171) = 6;
    v5 = a2;
  }
  v6 = *((_DWORD *)this + 171);
  if ( v6 != 6 )
  {
    v7 = 0;
    do
    {
      v8 = v6 - 1;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( v9 )
        {
          v10 = v9 - 1;
          if ( !v10 )
            goto LABEL_36;
          v11 = v10 - 1;
          if ( v11 )
          {
            if ( v11 != 1 )
              return -2147467259;
            *((_DWORD *)this + 171) = 6;
          }
          else
          {
            result = SSI_INCLUDE_FILE::ProcessSsiElements(this, a3);
            v5 = result;
            if ( result < 0 || *a3 || *((_DWORD *)this + 171) == 3 )
              return result;
          }
        }
        else
        {
          v13 = *((_QWORD *)this + 86);
          v14 = *((_QWORD *)this + 5);
          v33[0] = 200;
          v34 = 0;
          v35[0] = 0;
          v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 32LL))(v13);
          (*(void (__fastcall **)(__int64, unsigned __int16 *, __int16 *, _QWORD, _QWORD, unsigned int *, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v15 + 184LL))(
            v15,
            v33,
            &v34,
            0,
            0,
            v35,
            0,
            0,
            0,
            0);
          v16 = v35[0];
          if ( (v35[0] & 0x1FFF0000) == 0x70000 && (v35[0] & 0x80000000) != 0 )
            v16 = LOWORD(v35[0]);
          if ( v33[0] < 0x190u )
          {
            v7 = 0;
LABEL_36:
            *((_DWORD *)this + 171) = 4;
            goto LABEL_58;
          }
          v36[0] = *(char **)(*(_QWORD *)(v14 - 16) + 32LL);
          if ( v33[0] == 403 )
          {
            v7 = -1073739311;
          }
          else
          {
            if ( v16 )
            {
              switch ( *(_DWORD *)(v14 - 24) )
              {
                case 3:
                  v7 = -1073739314;
                  break;
                case 4:
                  v7 = -1073739313;
                  break;
                case 5:
                  v7 = -1073739312;
                  break;
              }
              v17 = v16;
            }
            else
            {
              v7 = -1073739305;
              v17 = v33[0];
            }
            _itoa_s(v17, Buffer, 0x20u, 10);
            v36[1] = Buffer;
          }
          *((_DWORD *)this + 171) = 4;
          if ( v7 )
          {
            result = SSI_REQUEST::SSISendError(*((SSI_REQUEST **)this + 2), v7, v36);
            v5 = result;
            if ( result < 0 )
              return result;
          }
        }
      }
      else
      {
        *((_DWORD *)this + 171) = 4;
        if ( !*((_QWORD *)this + 3) )
        {
          v18 = *((_QWORD *)this + 4);
          if ( *(_DWORD *)(*(_QWORD *)(v18 + 32) + 344LL) )
            return (*(__int64 (__fastcall **)(_QWORD, __int64, const char *))(**(_QWORD **)(*((_QWORD *)this + 2)
                                                                                          + 1096LL)
                                                                            + 32LL))(
                     *(_QWORD *)(*((_QWORD *)this + 2) + 1096LL),
                     12,
                     "text/html");
          v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v18 + 16) + 96LL))(*(_QWORD *)(v18 + 16), 0);
          v21 = v19;
          if ( v19 )
          {
            v22 = -1;
            do
              ++v22;
            while ( *(_BYTE *)(v19 + v22) );
            result = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(*((_QWORD *)this + 2) + 1096LL)
                                                                         + 32LL))(
                       *(_QWORD *)(*((_QWORD *)this + 2) + 1096LL),
                       22,
                       v19);
            if ( result < 0 )
              return result;
          }
          v23 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(*((_QWORD *)this + 4) + 16LL) + 112LL))(
                  *(_QWORD *)(*((_QWORD *)this + 4) + 16LL),
                  v20,
                  v21);
          if ( v23 )
          {
            v24 = -1;
            do
              ++v24;
            while ( *(_BYTE *)(v23 + v24) );
            result = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(*((_QWORD *)this + 2) + 1096LL)
                                                                         + 32LL))(
                       *(_QWORD *)(*((_QWORD *)this + 2) + 1096LL),
                       19,
                       v23);
            if ( result < 0 )
              return result;
          }
          result = (*(__int64 (__fastcall **)(_QWORD, __int64, const char *))(**(_QWORD **)(*((_QWORD *)this + 2)
                                                                                          + 1096LL)
                                                                            + 32LL))(
                     *(_QWORD *)(*((_QWORD *)this + 2) + 1096LL),
                     12,
                     "text/html");
          if ( result < 0 )
            return result;
          v25 = *((_QWORD *)this + 4);
          *(_QWORD *)v35 = 0;
          (*(void (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(v25 + 16) + 64LL))(*(_QWORD *)(v25 + 16), v35);
          if ( v35[1] )
            return -2147024846;
          v26 = *((_QWORD *)this + 4);
          v27 = *(_QWORD *)(v26 + 24);
          if ( !v27 )
            v27 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v26 + 16) + 72LL))(*(_QWORD *)(v26 + 16));
          v28 = *((_QWORD *)this + 4);
          v29 = *((_QWORD *)this + 2);
          if ( v27 )
          {
            v30 = *(char **)(v28 + 24);
            if ( !v30 )
              v30 = (char *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v28 + 16) + 72LL))(*(_QWORD *)(v28 + 16));
            v31 = SSI_VECTOR_BUFFER::AddToVector((SSI_VECTOR_BUFFER *)(v29 + 800), v30, v35[0]);
          }
          else
          {
            v32 = (void *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v28 + 16) + 80LL))(*(_QWORD *)(v28 + 16));
            v31 = SSI_VECTOR_BUFFER::AddFileChunkToVector((SSI_VECTOR_BUFFER *)(v29 + 800), 0, v35[0], v32);
          }
          v5 = v31;
          if ( v31 < 0 )
            return v5;
          *((_DWORD *)this + 171) = 5;
        }
      }
LABEL_58:
      v6 = *((_DWORD *)this + 171);
    }
    while ( v6 != 6 );
  }
  return v5;
}

```

## disassembly

```asm
0x1800042fc  mov     [rsp-8+arg_8], rbx
0x180004301  mov     [rsp-8+arg_18], rsi
0x180004306  push    rbp
0x180004307  push    rdi
0x180004308  push    r12
0x18000430a  push    r14
0x18000430c  push    r15
0x18000430e  lea     rbp, [rsp-37h]
0x180004313  sub     rsp, 0B0h
0x18000431a  mov     rax, cs:__security_cookie
0x180004321  xor     rax, rsp
0x180004324  mov     [rbp+57h+var_30], rax
0x180004328  xor     r12d, r12d
0x18000432b  xorps   xmm0, xmm0
0x18000432e  mov     [r8], r12d
0x180004331  mov     r15, r8
0x180004334  mov     rbx, rcx
0x180004337  mov     edi, 80004005h
0x18000433c  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x180004341  test    edx, edx
0x180004343  jns     short loc_18000435A
0x180004345  cmp     dword ptr [rcx+2ACh], 2
0x18000434c  jz      short loc_18000435A
0x18000434e  mov     dword ptr [rcx+2ACh], 6
0x180004358  mov     edi, edx
0x18000435a  mov     ecx, [rcx+2ACh]
0x180004360  cmp     ecx, 6
0x180004363  jz      loc_1800046DD
0x180004369  mov     esi, r12d
0x18000436c  sub     ecx, 1
0x18000436f  jz      loc_180004518
0x180004375  sub     ecx, 1
0x180004378  jz      short loc_1800043D0
0x18000437a  sub     ecx, 1
0x18000437d  jz      loc_180004509
0x180004383  sub     ecx, 1
0x180004386  jz      short loc_1800043A0
0x180004388  cmp     ecx, 1
0x18000438b  jnz     loc_180004707
0x180004391  mov     dword ptr [rbx+2ACh], 6
0x18000439b  jmp     loc_1800046CE
0x1800043a0  mov     rdx, r15; int *
0x1800043a3  mov     rcx, rbx; this
0x1800043a6  call    ?ProcessSsiElements@SSI_INCLUDE_FILE@@AEAAJPEAH@Z; SSI_INCLUDE_FILE::ProcessSsiElements(int *)
0x1800043ab  mov     edi, eax
0x1800043ad  test    eax, eax
0x1800043af  js      loc_1800046DF
0x1800043b5  cmp     [r15], r12d
0x1800043b8  jnz     loc_1800046DF
0x1800043be  cmp     dword ptr [rbx+2ACh], 3
0x1800043c5  jz      loc_1800046DF
0x1800043cb  jmp     loc_1800046CE
0x1800043d0  mov     rcx, [rbx+2B0h]
0x1800043d7  mov     eax, 0C8h
0x1800043dc  mov     r14, [rbx+28h]
0x1800043e0  mov     [rbp+57h+var_70], ax
0x1800043e4  mov     [rbp+57h+var_6C], r12w
0x1800043e9  mov     [rbp+57h+var_68], r12d
0x1800043ed  mov     rax, [rcx]
0x1800043f0  mov     rax, [rax+20h]
0x1800043f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043f9  mov     [rsp+0D0h+var_88], r12
0x1800043fe  lea     rdx, [rbp+57h+var_68]
0x180004402  mov     [rsp+0D0h+var_90], r12
0x180004407  lea     r8, [rbp+57h+var_6C]
0x18000440b  mov     rcx, rax
0x18000440e  mov     [rsp+0D0h+var_98], r12
0x180004413  mov     rax, [rax]
0x180004416  xor     r9d, r9d
0x180004419  mov     [rsp+0D0h+var_A0], r12
0x18000441e  mov     [rsp+0D0h+var_A8], rdx
0x180004423  lea     rdx, [rbp+57h+var_70]
0x180004427  mov     [rsp+0D0h+var_B0], r12
0x18000442c  mov     rax, [rax+0B8h]
0x180004433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004438  mov     r10d, [rbp+57h+var_68]
0x18000443c  mov     eax, r10d
0x18000443f  and     eax, 1FFF0000h
0x180004444  cmp     eax, 70000h
0x180004449  jnz     short loc_180004454
0x18000444b  test    r10d, r10d
0x18000444e  jns     short loc_180004454
0x180004450  movzx   r10d, r10w
0x180004454  movzx   edx, [rbp+57h+var_70]
0x180004458  mov     eax, 190h
0x18000445d  cmp     dx, ax
0x180004460  jb      loc_180004506
0x180004466  mov     rax, [r14-10h]
0x18000446a  mov     rcx, [rax+20h]
0x18000446e  mov     eax, 193h
0x180004473  mov     [rbp+57h+var_60], rcx
0x180004477  cmp     dx, ax
0x18000447a  jnz     short loc_180004483
0x18000447c  mov     esi, 0C00009D1h
0x180004481  jmp     short loc_1800044D6
0x180004483  test    r10d, r10d
0x180004486  jz      short loc_1800044B3
0x180004488  mov     ecx, [r14-18h]
0x18000448c  sub     ecx, 3
0x18000448f  jz      short loc_1800044A9
0x180004491  sub     ecx, 1
0x180004494  jz      short loc_1800044A2
0x180004496  cmp     ecx, 1
0x180004499  jnz     short loc_1800044AE
0x18000449b  mov     esi, 0C00009D0h
0x1800044a0  jmp     short loc_1800044AE
0x1800044a2  mov     esi, 0C00009CFh
0x1800044a7  jmp     short loc_1800044AE
0x1800044a9  mov     esi, 0C00009CEh
0x1800044ae  mov     ecx, r10d
0x1800044b1  jmp     short loc_1800044BA
0x1800044b3  mov     esi, 0C00009D7h
0x1800044b8  mov     ecx, edx; Value
0x1800044ba  mov     r9d, 0Ah; Radix
0x1800044c0  lea     rdx, [rbp+57h+Buffer]; Buffer
0x1800044c4  lea     r8d, [r9+16h]; BufferCount
0x1800044c8  call    cs:__imp__itoa_s
0x1800044ce  lea     rax, [rbp+57h+Buffer]
0x1800044d2  mov     [rbp+57h+var_60+8], rax
0x1800044d6  mov     dword ptr [rbx+2ACh], 4
0x1800044e0  test    esi, esi
0x1800044e2  jz      loc_1800046CE
0x1800044e8  mov     rcx, [rbx+10h]; this
0x1800044ec  lea     r8, [rbp+57h+var_60]; char **
0x1800044f0  mov     edx, esi; unsigned int
0x1800044f2  call    ?SSISendError@SSI_REQUEST@@QEAAJKQEAPEAD@Z; SSI_REQUEST::SSISendError(ulong,char * * const)
0x1800044f7  mov     edi, eax
0x1800044f9  test    eax, eax
0x1800044fb  js      loc_1800046DF
0x180004501  jmp     loc_1800046CE
0x180004506  mov     esi, r12d
0x180004509  mov     dword ptr [rbx+2ACh], 4
0x180004513  jmp     loc_1800046CE
0x180004518  mov     dword ptr [rbx+2ACh], 4
0x180004522  cmp     [rbx+18h], r12
0x180004526  jnz     loc_1800046CE
0x18000452c  mov     rcx, [rbx+20h]
0x180004530  mov     rax, [rcx+20h]
0x180004534  cmp     [rax+158h], r12d
0x18000453b  jnz     loc_180004715
0x180004541  mov     rcx, [rcx+10h]
0x180004545  xor     edx, edx
0x180004547  mov     rax, [rcx]
0x18000454a  mov     rax, [rax+60h]
0x18000454e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004553  mov     r8, rax
0x180004556  test    rax, rax
0x180004559  jz      short loc_180004591
0x18000455b  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000455f  inc     r9
0x180004562  cmp     [rax+r9], r12b
0x180004566  jnz     short loc_18000455F
0x180004568  mov     rax, [rbx+10h]
0x18000456c  mov     edx, 16h
0x180004571  mov     dword ptr [rsp+0D0h+var_B0], r12d
0x180004576  mov     rcx, [rax+448h]
0x18000457d  mov     rax, [rcx]
0x180004580  mov     rax, [rax+20h]
0x180004584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004589  test    eax, eax
0x18000458b  js      loc_1800046DF
0x180004591  mov     rax, [rbx+20h]
0x180004595  mov     rcx, [rax+10h]
0x180004599  mov     rax, [rcx]
0x18000459c  mov     rax, [rax+70h]
0x1800045a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045a5  mov     r8, rax
0x1800045a8  test    rax, rax
0x1800045ab  jz      short loc_1800045E3
0x1800045ad  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800045b1  inc     r9
0x1800045b4  cmp     [rax+r9], r12b
0x1800045b8  jnz     short loc_1800045B1
0x1800045ba  mov     rax, [rbx+10h]
0x1800045be  mov     edx, 13h
0x1800045c3  mov     dword ptr [rsp+0D0h+var_B0], r12d
0x1800045c8  mov     rcx, [rax+448h]
0x1800045cf  mov     rax, [rcx]
0x1800045d2  mov     rax, [rax+20h]
0x1800045d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045db  test    eax, eax
0x1800045dd  js      loc_1800046DF
0x1800045e3  mov     rax, [rbx+10h]
0x1800045e7  lea     r8, aTextHtml; "text/html"
0x1800045ee  mov     r9d, 9
0x1800045f4  mov     dword ptr [rsp+0D0h+var_B0], r12d
0x1800045f9  mov     rcx, [rax+448h]
0x180004600  lea     edx, [r9+3]
0x180004604  mov     rax, [rcx]
0x180004607  mov     rax, [rax+20h]
0x18000460b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004610  test    eax, eax
0x180004612  js      loc_1800046DF
0x180004618  mov     rax, [rbx+20h]
0x18000461c  lea     rdx, [rbp+57h+var_68]
0x180004620  mov     qword ptr [rbp+57h+var_68], r12
0x180004624  mov     rcx, [rax+10h]
0x180004628  mov     rax, [rcx]
0x18000462b  mov     rax, [rax+40h]
0x18000462f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004634  cmp     [rbp+57h+var_68+4], r12d
0x180004638  jnz     loc_18000470E
0x18000463e  mov     rax, [rbx+20h]
0x180004642  mov     rcx, [rax+18h]
0x180004646  test    rcx, rcx
0x180004649  jnz     short loc_18000465E
0x18000464b  mov     rcx, [rax+10h]
0x18000464f  mov     rax, [rcx]
0x180004652  mov     rax, [rax+48h]
0x180004656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000465b  mov     rcx, rax
0x18000465e  mov     rdx, [rbx+20h]
0x180004662  mov     rdi, [rbx+10h]
0x180004666  test    rcx, rcx
0x180004669  jz      short loc_180004699
0x18000466b  mov     rax, [rdx+18h]
0x18000466f  test    rax, rax
0x180004672  jnz     short loc_180004684
0x180004674  mov     rcx, [rdx+10h]
0x180004678  mov     rax, [rcx]
0x18000467b  mov     rax, [rax+48h]
0x18000467f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004684  mov     r8d, [rbp+57h+var_68]; unsigned int
0x180004688  lea     rcx, [rdi+320h]; this
0x18000468f  mov     rdx, rax; char *
0x180004692  call    ?AddToVector@SSI_VECTOR_BUFFER@@QEAAJPEADK@Z; SSI_VECTOR_BUFFER::AddToVector(char *,ulong)
0x180004697  jmp     short loc_1800046BE
0x180004699  mov     rcx, [rdx+10h]
0x18000469d  mov     rax, [rcx]
0x1800046a0  mov     rax, [rax+50h]
0x1800046a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046a9  mov     r8d, [rbp+57h+var_68]; unsigned int
0x1800046ad  lea     rcx, [rdi+320h]; this
0x1800046b4  mov     r9, rax; void *
0x1800046b7  xor     edx, edx; unsigned int
0x1800046b9  call    ?AddFileChunkToVector@SSI_VECTOR_BUFFER@@QEAAJKKPEAX@Z; SSI_VECTOR_BUFFER::AddFileChunkToVector(ulong,ulong,void *)
0x1800046be  mov     edi, eax
0x1800046c0  test    eax, eax
0x1800046c2  js      short loc_1800046DD
0x1800046c4  mov     dword ptr [rbx+2ACh], 5
0x1800046ce  mov     ecx, [rbx+2ACh]
0x1800046d4  cmp     ecx, 6
0x1800046d7  jnz     loc_18000436C
0x1800046dd  mov     eax, edi
0x1800046df  mov     rcx, [rbp+57h+var_30]
0x1800046e3  xor     rcx, rsp; StackCookie
0x1800046e6  call    __security_check_cookie
0x1800046eb  lea     r11, [rsp+0D0h+var_20]
0x1800046f3  mov     rbx, [r11+38h]
0x1800046f7  mov     rsi, [r11+48h]
0x1800046fb  mov     rsp, r11
0x1800046fe  pop     r15
0x180004700  pop     r14
0x180004702  pop     r12
0x180004704  pop     rdi
0x180004705  pop     rbp
0x180004706  retn
0x180004707  mov     eax, 80004005h
0x18000470c  jmp     short loc_1800046DF
0x18000470e  mov     eax, 80070032h
0x180004713  jmp     short loc_1800046DF
0x180004715  mov     rax, [rbx+10h]
0x180004719  lea     r8, aTextHtml; "text/html"
0x180004720  mov     r9d, 9
0x180004726  mov     dword ptr [rsp+0D0h+var_B0], r12d
0x18000472b  mov     rcx, [rax+448h]
0x180004732  lea     edx, [r9+3]
0x180004736  mov     rax, [rcx]
0x180004739  mov     rax, [rax+20h]
0x18000473d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004742  jmp     short loc_1800046DF
```
