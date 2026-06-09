# Session::CommitTransaction(Err &,ulong)

- ea: `0x10044950`
- end: `0x10044ca8`
- name: `?CommitTransaction@Session@@QAEXAAVErr@@K@Z`
- size: `856`
- prototype: `void __thiscall(Session *__hidden this, struct Err *, unsigned int)`
- caller_count: `16`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1001aaa0`
- `0x1001b180`
- `0x1001b2d0`
- `0x1002d300`
- `0x10037550`
- `0x1004a9a0`
- `0x10050bc0`
- `0x10052140`
- `0x10052e30`
- `0x10053950`
- `0x100544e0`
- `0x10054e90`
- `0x10055260`
- `0x10055ed0`
- `0x10056280`
- `0x1005b290`

## callees

- `0x1000eb60`
- `0x1000f750`
- `0x10012db0`
- `0x10012dd0`
- `0x100374c0`
- `0x10044950`
- `0x1004eda0`
- `0x10051e80`
- `0x10052320`
- `0x100592b0`
- `0x1005d310`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e7e8`
- `0x1005e7f3`
- `0x1005f064`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10044c17`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10044c17`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x10044c04`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x10044c04`

## pseudocode

```c
void __thiscall Session::CommitTransaction(Session *this, void **a2, char a3)
{
  int v4; // esi
  struct Err *v5; // edx
  int v6; // esi
  int v7; // eax
  int v8; // ecx
  int v9; // edi
  IAccMeth *v10; // esi
  unsigned int v11; // ecx
  int v12; // ecx
  int v13; // eax
  int v14; // edi
  Table *v15; // esi
  unsigned int v16; // edi
  unsigned int v17; // esi
  _DWORD *v18; // ecx
  int v19; // edx
  int v20; // esi
  unsigned int j; // eax
  int k; // edi
  int v23; // esi
  struct Err *v24; // ecx
  DWORD TickCount; // eax
  unsigned int v26; // ecx
  int m; // edx
  _DWORD *v28; // eax
  int v29; // [esp-8h] [ebp-48h]
  int v30[3]; // [esp+10h] [ebp-30h] BYREF
  void *Block; // [esp+1Ch] [ebp-24h]
  void *v32; // [esp+20h] [ebp-20h]
  _DWORD *v33; // [esp+24h] [ebp-1Ch] BYREF
  unsigned int v34; // [esp+28h] [ebp-18h]
  unsigned int v35; // [esp+2Ch] [ebp-14h]
  int i; // [esp+30h] [ebp-10h]
  int v37; // [esp+3Ch] [ebp-4h]

  v4 = *((_DWORD *)this + 5) - 1;
  if ( *((int *)this + 14) > 0 )
  {
    v5 = (struct Err *)a2;
    if ( v4 < 0 )
    {
LABEL_12:
      v6 = *((_DWORD *)this + 14);
      if ( *((_DWORD *)this + 3 * v6 + 17) == *((_DWORD *)this + 3 * v6 + 14) )
        goto LABEL_25;
      if ( (a3 & 2) != 0 )
        v7 = 1;
      else
        v7 = *((_DWORD *)this + 3 * v6 + 15);
      v8 = 0;
      if ( (a3 & 8) == 0 )
        v8 = v7;
      v9 = *((_DWORD *)this + 52) - 1;
      i = v8;
      if ( v9 < 0 )
      {
LABEL_25:
        v12 = *((_DWORD *)this + 8);
        if ( v12 )
        {
          do
          {
            v13 = *((_DWORD *)this + 6);
            v29 = *((_DWORD *)this + 14);
            i = v12 - 1;
            (*(void (__thiscall **)(_DWORD, int, struct Err *))(**(_DWORD **)(v13 + 4 * (v12 - 1)) + 40))(
              *(_DWORD *)(v13 + 4 * (v12 - 1)),
              v29,
              v5);
            v12 = i;
            v5 = (struct Err *)a2;
          }
          while ( i );
        }
        v14 = *((_DWORD *)this + 5) - 1;
        if ( v14 < 0 )
        {
LABEL_36:
          if ( (a3 & 8) != 0 )
          {
            v30[0] = 1;
            v37 = 0;
            v16 = 0;
            v17 = *((_DWORD *)this + 52);
            v35 = 0;
            v18 = operator new[](4 * v17 + 4);
            v34 = v17;
            v33 = v18;
            LOBYTE(v37) = 1;
            v19 = *((_DWORD *)this + 52) - 1;
            for ( i = v19; v19 >= 0; i = v19 )
            {
              v20 = *(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 50) + 4 * v19) + 8);
              for ( j = 0; j < v16; ++j )
              {
                if ( v18[j] == v20 )
                  break;
              }
              if ( j == v16 )
              {
                if ( v16 < v34
                  || (Collection::Grow((Collection *)&v33, v16 + 1, (struct Err *)v30),
                      v16 = v35,
                      v18 = v33,
                      v19 = i,
                      (v30[0] & 8) == 0) )
                {
                  v18[v16++] = v20;
                  v35 = v16;
                }
              }
              --v19;
            }
            for ( k = v16 - 1; k >= 0; --k )
            {
              v23 = v18[k];
              if ( *(_DWORD *)(v23 + 172) < *(_DWORD *)(v23 + 184) )
              {
                if ( !FlushFileBuffers(*(HANDLE *)(v23 + 4)) )
                  System::ErrGetLastError(v24);
                TickCount = GetTickCount();
                v18 = v33;
                *(_DWORD *)(v23 + 172) = TickCount;
              }
            }
            if ( v18 )
              operator delete[](v18);
            if ( (v30[0] & 0xFFFFFFFE) != 0 )
            {
              if ( Block )
                operator delete[](Block);
              if ( v32 )
                operator delete[](v32);
            }
          }
          if ( (*(_BYTE *)a2 & 8) == 0 )
          {
            --*((_DWORD *)this + 14);
            v26 = 0;
            for ( m = *((_DWORD *)this + 3 * *((_DWORD *)this + 14) + 17); v26 < *((_DWORD *)this + 52); *v28 = m )
              v28 = *(_DWORD **)(*((_DWORD *)this + 50) + 4 * v26++);
          }
        }
        else
        {
          while ( 1 )
          {
            v15 = *(Table **)(*((_DWORD *)this + 3) + 4 * v14);
            if ( *((_DWORD *)v15 + 17) == -1 && *((_DWORD *)this + 14) == 1 )
            {
              if ( *(_DWORD *)(*((_DWORD *)v15 + 9) + 68) != 1 )
                Table::DropNotify(v15, this);
              if ( !*((_DWORD *)v15 + 19) )
              {
                Table::~Table(v15);
                operator delete(v15, 0x778u);
              }
            }
            if ( (*(_BYTE *)a2 & 8) != 0 )
              break;
            if ( --v14 < 0 )
              goto LABEL_36;
          }
        }
      }
      else
      {
        while ( 1 )
        {
          v10 = *(IAccMeth **)(*((_DWORD *)this + 50) + 4 * v9);
          dword_10066970 = 1;
          Transaction::Commit(v10, v8, v5);
          v5 = (struct Err *)a2;
          if ( *(_DWORD *)v10 == 1 && (*(_BYTE *)a2 & 8) == 0 && !*((_DWORD *)v10 + 11) )
          {
            IAccMeth::`scalar deleting destructor'(v10, v11);
            v5 = (struct Err *)a2;
          }
          dword_10066970 = 0;
          if ( (*(_BYTE *)v5 & 8) != 0 )
            break;
          --v9;
          v8 = i;
          if ( v9 < 0 )
            goto LABEL_25;
        }
      }
    }
    else
    {
      while ( 1 )
      {
        Table::CommitPrePages(*(Table **)(*((_DWORD *)this + 3) + 4 * v4), this, v5);
        v5 = (struct Err *)a2;
        if ( (*(_BYTE *)a2 & 8) != 0 )
          break;
        if ( --v4 < 0 )
          goto LABEL_12;
      }
    }
  }
  else if ( (int)*a2 < 8 )
  {
    if ( ((unsigned int)*a2 & 0xFFFFFFFE) != 0 )
    {
      if ( a2[3] )
        operator delete[](a2[3]);
      if ( a2[4] )
        operator delete[](a2[4]);
    }
    *a2 = (void *)8;
    a2[1] = (void *)-1054;
    a2[2] = 0;
    a2[3] = 0;
    a2[4] = 0;
  }
}

```

## disassembly

```asm
0x10044950  mov     edi, edi
0x10044952  push    ebp
0x10044953  mov     ebp, esp
0x10044955  push    0FFFFFFFFh
0x10044957  push    offset ?CommitTransaction@Session@@QAEXAAVErr@@K@Z_SEH
0x1004495c  mov     eax, large fs:0
0x10044962  push    eax
0x10044963  sub     esp, 24h
0x10044966  push    ebx
0x10044967  push    esi
0x10044968  push    edi
0x10044969  mov     eax, ___security_cookie
0x1004496e  xor     eax, ebp
0x10044970  push    eax
0x10044971  lea     eax, [ebp+var_C]
0x10044974  mov     large fs:0, eax
0x1004497a  mov     ebx, ecx
0x1004497c  mov     esi, [ebx+14h]
0x1004497f  dec     esi
0x10044980  cmp     dword ptr [ebx+38h], 0
0x10044984  jg      short loc_100449F1
0x10044986  mov     esi, [ebp+arg_0]
0x10044989  mov     eax, [esi]
0x1004498b  cmp     eax, 8
0x1004498e  jge     loc_10044C94
0x10044994  test    eax, 0FFFFFFFEh
0x10044999  jz      short loc_100449BB
0x1004499b  mov     eax, [esi+0Ch]
0x1004499e  test    eax, eax
0x100449a0  jz      short loc_100449AB
0x100449a2  push    eax; Block
0x100449a3  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100449a8  add     esp, 4
0x100449ab  mov     eax, [esi+10h]
0x100449ae  test    eax, eax
0x100449b0  jz      short loc_100449BB
0x100449b2  push    eax; Block
0x100449b3  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100449b8  add     esp, 4
0x100449bb  mov     dword ptr [esi], 8
0x100449c1  mov     dword ptr [esi+4], 0FFFFFBE2h
0x100449c8  mov     dword ptr [esi+8], 0
0x100449cf  mov     dword ptr [esi+0Ch], 0
0x100449d6  mov     dword ptr [esi+10h], 0
0x100449dd  mov     ecx, [ebp+var_C]
0x100449e0  mov     large fs:0, ecx
0x100449e7  pop     ecx
0x100449e8  pop     edi
0x100449e9  pop     esi
0x100449ea  pop     ebx
0x100449eb  mov     esp, ebp
0x100449ed  pop     ebp
0x100449ee  retn    8
0x100449f1  mov     edx, [ebp+arg_0]
0x100449f4  test    esi, esi
0x100449f6  js      short loc_10044A16
0x100449f8  mov     eax, [ebx+0Ch]
0x100449fb  push    edx; struct Err *
0x100449fc  push    ebx; struct Session *
0x100449fd  mov     ecx, [eax+esi*4]; this
0x10044a00  call    ?CommitPrePages@Table@@QAEXPAVSession@@AAVErr@@@Z; Table::CommitPrePages(Session *,Err &)
0x10044a05  mov     edx, [ebp+arg_0]
0x10044a08  test    byte ptr [edx], 8
0x10044a0b  jnz     loc_10044C94
0x10044a11  sub     esi, 1
0x10044a14  jns     short loc_100449F8
0x10044a16  mov     esi, [ebx+38h]
0x10044a19  lea     eax, [esi+esi*2]
0x10044a1c  lea     ecx, [ebx+eax*4]
0x10044a1f  mov     eax, [ecx+44h]
0x10044a22  cmp     eax, [ecx+38h]
0x10044a25  mov     ecx, [ebp+arg_4]
0x10044a28  jz      loc_10044AB5
0x10044a2e  test    cl, 2
0x10044a31  jz      short loc_10044A3A
0x10044a33  mov     eax, 1
0x10044a38  jmp     short loc_10044A41
0x10044a3a  lea     eax, [esi+esi*2]
0x10044a3d  mov     eax, [ebx+eax*4+3Ch]
0x10044a41  mov     edi, [ebx+0D0h]
0x10044a47  test    cl, 8
0x10044a4a  mov     ecx, 0
0x10044a4f  cmovz   ecx, eax
0x10044a52  sub     edi, 1
0x10044a55  mov     [ebp+var_10], ecx
0x10044a58  js      short loc_10044AB5
0x10044a5a  nop     word ptr [eax+eax+00h]
0x10044a60  mov     eax, [ebx+0C8h]
0x10044a66  push    edx
0x10044a67  push    ecx
0x10044a68  mov     esi, [eax+edi*4]
0x10044a6b  mov     ecx, esi
0x10044a6d  mov     dword_10066970, 1
0x10044a77  call    ?Commit@Transaction@@QAEXW4TransactionType@@AAVErr@@@Z; Transaction::Commit(TransactionType,Err &)
0x10044a7c  cmp     dword ptr [esi], 1
0x10044a7f  mov     edx, [ebp+arg_0]
0x10044a82  jnz     short loc_10044A9A
0x10044a84  test    byte ptr [edx], 8
0x10044a87  jnz     short loc_10044A9A
0x10044a89  cmp     dword ptr [esi+2Ch], 0
0x10044a8d  jnz     short loc_10044A9A
0x10044a8f  push    ecx; unsigned int
0x10044a90  mov     ecx, esi; this
0x10044a92  call    ??_GIAccMeth@@AAEPAXI@Z; IAccMeth::`scalar deleting destructor'(uint)
0x10044a97  mov     edx, [ebp+arg_0]
0x10044a9a  mov     dword_10066970, 0
0x10044aa4  test    byte ptr [edx], 8
0x10044aa7  jnz     loc_10044C94
0x10044aad  sub     edi, 1
0x10044ab0  mov     ecx, [ebp+var_10]
0x10044ab3  jns     short loc_10044A60
0x10044ab5  mov     ecx, [ebx+20h]
0x10044ab8  test    ecx, ecx
0x10044aba  jz      short loc_10044AE9
0x10044abc  nop     dword ptr [eax+00h]
0x10044ac0  mov     eax, [ebx+18h]
0x10044ac3  dec     ecx
0x10044ac4  push    edx; unsigned int
0x10044ac5  push    dword ptr [ebx+38h]; void *
0x10044ac8  mov     [ebp+var_10], ecx
0x10044acb  mov     edi, [eax+ecx*4]
0x10044ace  mov     eax, [edi]
0x10044ad0  mov     esi, [eax+28h]
0x10044ad3  mov     ecx, esi
0x10044ad5  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10044adb  mov     ecx, edi
0x10044add  call    esi
0x10044adf  mov     ecx, [ebp+var_10]
0x10044ae2  mov     edx, [ebp+arg_0]
0x10044ae5  test    ecx, ecx
0x10044ae7  jnz     short loc_10044AC0
0x10044ae9  mov     edi, [ebx+14h]
0x10044aec  sub     edi, 1
0x10044aef  js      short loc_10044B40
0x10044af1  mov     eax, [ebx+0Ch]
0x10044af4  mov     esi, [eax+edi*4]
0x10044af7  cmp     dword ptr [esi+44h], 0FFFFFFFFh
0x10044afb  jnz     short loc_10044B2F
0x10044afd  cmp     dword ptr [ebx+38h], 1
0x10044b01  jnz     short loc_10044B2F
0x10044b03  mov     eax, [esi+24h]
0x10044b06  cmp     dword ptr [eax+44h], 1
0x10044b0a  jz      short loc_10044B14
0x10044b0c  push    ebx; struct Session *
0x10044b0d  mov     ecx, esi; this
0x10044b0f  call    ?DropNotify@Table@@AAEXPAVSession@@@Z; Table::DropNotify(Session *)
0x10044b14  cmp     dword ptr [esi+4Ch], 0
0x10044b18  jnz     short loc_10044B2F
0x10044b1a  mov     ecx, esi; this
0x10044b1c  call    ??1Table@@QAE@XZ; Table::~Table(void)
0x10044b21  push    778h; unsigned int
0x10044b26  push    esi; Block
0x10044b27  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x10044b2c  add     esp, 8
0x10044b2f  mov     eax, [ebp+arg_0]
0x10044b32  test    byte ptr [eax], 8
0x10044b35  jnz     loc_10044C94
0x10044b3b  sub     edi, 1
0x10044b3e  jns     short loc_10044AF1
0x10044b40  test    byte ptr [ebp+arg_4], 8
0x10044b44  jz      loc_10044C61
0x10044b4a  mov     [ebp+var_30], 1
0x10044b51  mov     [ebp+var_4], 0
0x10044b58  xor     edi, edi
0x10044b5a  mov     esi, [ebx+0D0h]
0x10044b60  mov     [ebp+var_14], edi
0x10044b63  lea     eax, ds:4[esi*4]
0x10044b6a  push    eax; unsigned int
0x10044b6b  call    ??_U@YAPAXI@Z; operator new[](uint)
0x10044b70  mov     ecx, eax
0x10044b72  mov     [ebp+var_18], esi
0x10044b75  add     esp, 4
0x10044b78  mov     [ebp+var_1C], ecx
0x10044b7b  mov     byte ptr [ebp+var_4], 1
0x10044b7f  mov     edx, [ebx+0D0h]
0x10044b85  sub     edx, 1
0x10044b88  mov     [ebp+var_10], edx
0x10044b8b  js      short loc_10044BE3
0x10044b8d  nop     dword ptr [eax]
0x10044b90  mov     eax, [ebx+0C8h]
0x10044b96  mov     eax, [eax+edx*4]
0x10044b99  mov     esi, [eax+8]
0x10044b9c  xor     eax, eax
0x10044b9e  test    edi, edi
0x10044ba0  jz      short loc_10044BAC
0x10044ba2  cmp     [ecx+eax*4], esi
0x10044ba5  jz      short loc_10044BAC
0x10044ba7  inc     eax
0x10044ba8  cmp     eax, edi
0x10044baa  jb      short loc_10044BA2
0x10044bac  cmp     eax, edi
0x10044bae  jnz     short loc_10044BDB
0x10044bb0  cmp     edi, [ebp+var_18]
0x10044bb3  jb      short loc_10044BD4
0x10044bb5  lea     eax, [ebp+var_30]
0x10044bb8  push    eax; struct Err *
0x10044bb9  lea     eax, [edi+1]
0x10044bbc  push    eax; unsigned int
0x10044bbd  lea     ecx, [ebp+var_1C]; this
0x10044bc0  call    ?Grow@Collection@@QAEXKAAVErr@@@Z; Collection::Grow(ulong,Err &)
0x10044bc5  test    byte ptr [ebp+var_30], 8
0x10044bc9  mov     edi, [ebp+var_14]
0x10044bcc  mov     ecx, [ebp+var_1C]
0x10044bcf  mov     edx, [ebp+var_10]
0x10044bd2  jnz     short loc_10044BDB
0x10044bd4  mov     [ecx+edi*4], esi
0x10044bd7  inc     edi
0x10044bd8  mov     [ebp+var_14], edi
0x10044bdb  sub     edx, 1
0x10044bde  mov     [ebp+var_10], edx
0x10044be1  jns     short loc_10044B90
0x10044be3  add     edi, 0FFFFFFFFh
0x10044be6  js      short loc_10044C2B
0x10044be8  nop     dword ptr [eax+eax+00000000h]
0x10044bf0  mov     esi, [ecx+edi*4]
0x10044bf3  mov     eax, [esi+0ACh]
0x10044bf9  cmp     eax, [esi+0B8h]
0x10044bff  jnb     short loc_10044C26
0x10044c01  push    dword ptr [esi+4]; hFile
0x10044c04  call    ds:__imp__FlushFileBuffers@4; FlushFileBuffers(x)
0x10044c0a  test    eax, eax
0x10044c0c  jnz     short loc_10044C17
0x10044c0e  lea     eax, [ebp+var_30]
0x10044c11  push    eax
0x10044c12  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x10044c17  call    ds:__imp__GetTickCount@0; GetTickCount()
0x10044c1d  mov     ecx, [ebp+var_1C]
0x10044c20  mov     [esi+0ACh], eax
0x10044c26  sub     edi, 1
0x10044c29  jns     short loc_10044BF0
0x10044c2b  test    ecx, ecx
0x10044c2d  jz      short loc_10044C38
0x10044c2f  push    ecx; Block
0x10044c30  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10044c35  add     esp, 4
0x10044c38  test    [ebp+var_30], 0FFFFFFFEh
0x10044c3f  jz      short loc_10044C61
0x10044c41  mov     eax, [ebp+Block]
0x10044c44  test    eax, eax
0x10044c46  jz      short loc_10044C51
0x10044c48  push    eax; Block
0x10044c49  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10044c4e  add     esp, 4
0x10044c51  mov     eax, [ebp+var_20]
0x10044c54  test    eax, eax
0x10044c56  jz      short loc_10044C61
0x10044c58  push    eax; Block
0x10044c59  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10044c5e  add     esp, 4
0x10044c61  mov     eax, [ebp+arg_0]
0x10044c64  test    byte ptr [eax], 8
0x10044c67  jnz     short loc_10044C94
0x10044c69  dec     dword ptr [ebx+38h]
0x10044c6c  xor     ecx, ecx
0x10044c6e  mov     eax, [ebx+38h]
0x10044c71  lea     eax, [eax+eax*2]
0x10044c74  mov     edx, [ebx+eax*4+44h]
0x10044c78  cmp     [ebx+0D0h], ecx
0x10044c7e  jbe     short loc_10044C94
0x10044c80  mov     eax, [ebx+0C8h]
0x10044c86  mov     eax, [eax+ecx*4]
0x10044c89  inc     ecx
0x10044c8a  mov     [eax], edx
0x10044c8c  cmp     ecx, [ebx+0D0h]
0x10044c92  jb      short loc_10044C80
0x10044c94  mov     ecx, [ebp+var_C]
0x10044c97  mov     large fs:0, ecx
0x10044c9e  pop     ecx
0x10044c9f  pop     edi
0x10044ca0  pop     esi
0x10044ca1  pop     ebx
0x10044ca2  mov     esp, ebp
0x10044ca4  pop     ebp
0x10044ca5  retn    8
0x10061460  lea     ecx, [ebp+var_30]; this
0x10061463  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x10061468  lea     ecx, [ebp+var_1C]; this
0x1006146b  jmp     ??1PresOrderList@@QAE@XZ; PresOrderList::~PresOrderList(void)
0x10061475  nop
0x10061476  nop
0x10061477  mov     edx, [esp-4+arg_4]
0x1006147b  lea     eax, [edx+0Ch]
0x1006147e  mov     ecx, [edx-34h]
0x10061481  xor     ecx, eax; StackCookie
0x10061483  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10061488  mov     eax, offset stru_10063EC0
0x1006148d  jmp     ___CxxFrameHandler3
```
