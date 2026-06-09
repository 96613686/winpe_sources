# ShlPlaceOT(HDC__ *,void * *,ushort const *,int,tag_SCRIPT_VISATTR const *,tag_SCRIPT_ANALYSIS *,wchar_t const *,int,ushort *,script_charprop *,ulong,ulong,int *,textrange_properties * *,int,int *,tagGOFFSET *,_ABC *)

- ea: `0x180006880`
- end: `0x1800070e6`
- name: `?ShlPlaceOT@@YAJPEAUHDC__@@PEAPEAXPEBGHPEBUtag_SCRIPT_VISATTR@@PEAUtag_SCRIPT_ANALYSIS@@PEB_WHPEAGPEAUscript_charprop@@KKPEAHPEAPEAUtextrange_properties@@H8PEAUtagGOFFSET@@PEAU_ABC@@@Z`
- size: `2150`
- prototype: `__int64 __fastcall(HDC, void **, const unsigned __int16 *, int, const struct tag_SCRIPT_VISATTR *, struct tag_SCRIPT_ANALYSIS *, const wchar_t *, int, unsigned __int16 *, struct script_charprop *, unsigned int, unsigned int, int *, struct textrange_properties **, int, int *, struct tagGOFFSET *, struct _ABC *)`
- caller_count: `5`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x1800040d0`
- `0x180005cc0`
- `0x180006150`
- `0x180007760`
- `0x18003dba0`

## callees

- `0x180004d2c`
- `0x180005638`
- `0x180005670`
- `0x180005940`
- `0x180006880`
- `0x180009d00`
- `0x18000e404`
- `0x18000e480`
- `0x18007ac50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006e76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006ec1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006e76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006ec1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006e50`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006e9b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006e50`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006e9b`
- `TextShaping!ShapingGetGlyphPositions` at `0x180006ac6`
- `TextShaping!ShapingGetGlyphPositions` at `0x180006ac6`

## string_xrefs

- `0x180006995`: `dfltlatnlatnlatnlatnlatnlatngrekcyrlarmngeorlatndfltDFLTkanakanakanahanihanghangbopoyi  hanidflthebrhebrarabarabarabarabsyrcthaithaithaidev2dev2tml2tml2bng2bng2bng2gur2gur2gjr2gjr2gjr2ory2ory2tel2tel2knd2knd2mlm2mlm2tibttibtlao lao khmrkhmrmym2mymrmongmongethiethithaacanscherbrairunrogamsinhlatndflttaletalutaluphagnko dsrtmathosmaosmatfngvai vai lisulatnglagitalgothorkhqavsbugijavacoptolckolcksoratglghanobuhdtagblimblimbbalibalisundsundlepclepcsylosaursaurkalikalirjngchamchamlinblycicariugarxpeo`

## pseudocode

```c

```
