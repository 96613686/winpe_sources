# MkvMfSourceLib::InitializeTagMaps

- ea: `0x18002a9b8`
- end: `0x18002bb1f`
- name: `MkvMfSourceLib::InitializeTagMaps`
- size: `4455`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002bb28`

## callees

- `0x180002400`
- `0x180008da0`
- `0x18000acc0`
- `0x1800298e0`
- `0x18002a06c`
- `0x18002a134`
- `0x18002a9b8`

## string_xrefs

- `0x18002aa50`: `ACCOMPANIMENT`
- `0x18002aa85`: `COMPOSER`
- `0x18002b58b`: `COMPOSITION_LOCATION`
- `0x18002b5f5`: `COMMENT`
- `0x18002b5c0`: `COMPOSER_NATIONALITY`
- `0x18002b8c2`: `PRODUCTION_COPYRIGHT`
- `0x18002b886`: `COPYRIGHT`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 MkvMfSourceLib::InitializeTagMaps()
{
  const char *v0; // r9
  __int64 result; // rax
  _BYTE v2[16]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v3[32]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  try
  {
    std::wstring::wstring(v3, L"ARTIST");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Music_Artist;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"LEAD_PERFORMER");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"ACCOMPANIMENT");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"COMPOSER");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Music_Composer;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"ARRANGER");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"LYRICS");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Music_Lyrics;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"LYRICIST");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"CONDUCTOR");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Music_Conductor;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"DIRECTOR");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Video_Director;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"ASSISTANT_DIRECTOR");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"DIRECTOR_OF_PHOTOGRAPHY");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"SOUND_ENGINEER");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"ART_DIRECTOR");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"PRODUCTION_DESIGNER");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"CHOREGRAPHER");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"COSTUME_DESIGNER");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"ACTOR");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"CHARACTER");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"WRITTEN_BY");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Media_Writer;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"SCREENPLAY_BY");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"EDITED_BY");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"PRODUCER");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Media_Producer;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"COPRODUCER");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"EXECUTIVE_PRODUCER");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"DISTRIBUTED_BY");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"MASTERED_BY");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"ENCODED_BY");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Media_EncodedBy;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"MIXED_BY");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"REMIXED_BY");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"PRODUCTION_STUDIO");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"THANKS_TO");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"PUBLISHER");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Media_Publisher;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"LABEL");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"GENRE");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Music_Genre;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"MOOD");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Music_Mood;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"ORIGINAL_MEDIA_TYPE");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"CONTENT_TYPE");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"SUBJECT");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"DESCRIPTION");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Comment;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"KEYWORDS");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Keywords;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"SUMMARY");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"SYNOPSIS");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"INITIAL_KEY");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Music_InitialKey;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"PERIOD");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Music_Period;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"LAW_RATING");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_ParentalRating;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"ICRA");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"DATE_RELEASED");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Media_DateReleased;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"DATE_RECORDED");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"DATE_ENCODED");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Media_DateEncoded;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"DATE_TAGGED");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"DATE_DIGITIZED");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"DATE_WRITTEN");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"DATE_PURCHASED");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"RECORDING_LOCATION");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"COMPOSITION_LOCATION");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"COMPOSER_NATIONALITY");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"COMMENT");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Comment;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"PLAY_COUNTER");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"RATING");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Rating;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"ENCODER");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"ENCODER_SETTINGS");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Media_EncodingSettings;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"BPS");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"FPS");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"BPM");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Music_BeatsPerMinute;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"MEASURE");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"TUNING");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"REPLAYGAIN_GAIN");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"REPLAYGAIN_PEAK");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"COPYRIGHT");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Copyright;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"PRODUCTION_COPYRIGHT");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"LICENSE");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"TERMS_OF_USE");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"TITLE");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Title;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"SUBTITLE");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800DBEC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Media_SubTitle;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"TITLE");
    MkvMfSourceLib::AddAudioTag(50, v3, &PKEY_Music_AlbumTitle);
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"ARTIST");
    MkvMfSourceLib::AddAudioTag(50, v3, &PKEY_Music_AlbumArtist);
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"PART_NUMBER");
    MkvMfSourceLib::AddAudioTag(30, v3, &PKEY_Music_TrackNumber);
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"PART_NUMBER");
    MkvMfSourceLib::AddAudioTag(40, v3, &PKEY_Music_PartOfSet);
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"PART_NUMBER");
    MkvMfSourceLib::AddVideoTag(60, v3, &PKEY_Media_SeasonNumber);
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"PART_NUMBER");
    MkvMfSourceLib::AddVideoTag(50, v3, &PKEY_Media_EpisodeNumber);
    std::wstring::_Tidy_deallocate(v3);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x16C,
                           (unsigned int)"avcore\\mf\\core\\mediasource\\mkv\\lib\\mkvmetadata.cpp",
                           v0);
  }
  return result;
}

```

## disassembly

```asm
0x18002a9b8  mov     [rsp+arg_0], rbx
0x18002a9bd  mov     [rsp+arg_8], rsi
0x18002a9c2  push    rdi
0x18002a9c3  sub     rsp, 60h
0x18002a9c7  mov     rax, cs:__security_cookie
0x18002a9ce  xor     rax, rsp
0x18002a9d1  mov     [rsp+68h+var_10], rax
0x18002a9d6  lea     rdx, aArtist; "ARTIST"
0x18002a9dd  lea     rcx, [rsp+68h+var_30]
0x18002a9e2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002a9e7  nop
0x18002a9e8  lea     r8, [rsp+68h+var_30]
0x18002a9ed  lea     rdx, [rsp+68h+var_48]
0x18002a9f2  lea     rbx, qword_1800DBEC0
0x18002a9f9  mov     rcx, rbx
0x18002a9fc  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002aa01  mov     rax, [rax]
0x18002aa04  lea     rcx, PKEY_Music_Artist
0x18002aa0b  mov     [rax+40h], rcx
0x18002aa0f  lea     rcx, [rsp+68h+var_30]
0x18002aa14  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002aa19  lea     rdx, aLeadPerformer; "LEAD_PERFORMER"
0x18002aa20  lea     rcx, [rsp+68h+var_30]
0x18002aa25  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002aa2a  nop
0x18002aa2b  lea     r8, [rsp+68h+var_30]
0x18002aa30  lea     rdx, [rsp+68h+var_48]
0x18002aa35  mov     rcx, rbx
0x18002aa38  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002aa3d  mov     rax, [rax]
0x18002aa40  xor     edi, edi
0x18002aa42  mov     [rax+40h], rdi
0x18002aa46  lea     rcx, [rsp+68h+var_30]
0x18002aa4b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002aa50  lea     rdx, aAccompaniment; "ACCOMPANIMENT"
0x18002aa57  lea     rcx, [rsp+68h+var_30]
0x18002aa5c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002aa61  nop
0x18002aa62  lea     r8, [rsp+68h+var_30]
0x18002aa67  lea     rdx, [rsp+68h+var_48]
0x18002aa6c  mov     rcx, rbx
0x18002aa6f  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002aa74  mov     rax, [rax]
0x18002aa77  mov     [rax+40h], rdi
0x18002aa7b  lea     rcx, [rsp+68h+var_30]
0x18002aa80  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002aa85  lea     rdx, aComposer; "COMPOSER"
0x18002aa8c  lea     rcx, [rsp+68h+var_30]
0x18002aa91  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002aa96  nop
0x18002aa97  lea     r8, [rsp+68h+var_30]
0x18002aa9c  lea     rdx, [rsp+68h+var_48]
0x18002aaa1  mov     rcx, rbx
0x18002aaa4  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002aaa9  mov     rax, [rax]
0x18002aaac  lea     rcx, PKEY_Music_Composer
0x18002aab3  mov     [rax+40h], rcx
0x18002aab7  lea     rcx, [rsp+68h+var_30]
0x18002aabc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002aac1  lea     rdx, aArranger; "ARRANGER"
0x18002aac8  lea     rcx, [rsp+68h+var_30]
0x18002aacd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002aad2  nop
0x18002aad3  lea     r8, [rsp+68h+var_30]
0x18002aad8  lea     rdx, [rsp+68h+var_48]
0x18002aadd  mov     rcx, rbx
0x18002aae0  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002aae5  mov     rax, [rax]
0x18002aae8  mov     [rax+40h], rdi
0x18002aaec  lea     rcx, [rsp+68h+var_30]
0x18002aaf1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002aaf6  lea     rdx, aLyrics; "LYRICS"
0x18002aafd  lea     rcx, [rsp+68h+var_30]
0x18002ab02  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002ab07  nop
0x18002ab08  lea     r8, [rsp+68h+var_30]
0x18002ab0d  lea     rdx, [rsp+68h+var_48]
0x18002ab12  mov     rcx, rbx
0x18002ab15  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002ab1a  mov     rax, [rax]
0x18002ab1d  lea     rcx, PKEY_Music_Lyrics
0x18002ab24  mov     [rax+40h], rcx
0x18002ab28  lea     rcx, [rsp+68h+var_30]
0x18002ab2d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ab32  lea     rdx, aLyricist; "LYRICIST"
0x18002ab39  lea     rcx, [rsp+68h+var_30]
0x18002ab3e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002ab43  nop
0x18002ab44  lea     r8, [rsp+68h+var_30]
0x18002ab49  lea     rdx, [rsp+68h+var_48]
0x18002ab4e  mov     rcx, rbx
0x18002ab51  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002ab56  mov     rax, [rax]
0x18002ab59  mov     [rax+40h], rdi
0x18002ab5d  lea     rcx, [rsp+68h+var_30]
0x18002ab62  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ab67  lea     rdx, aConductor; "CONDUCTOR"
0x18002ab6e  lea     rcx, [rsp+68h+var_30]
0x18002ab73  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002ab78  nop
0x18002ab79  lea     r8, [rsp+68h+var_30]
0x18002ab7e  lea     rdx, [rsp+68h+var_48]
0x18002ab83  mov     rcx, rbx
0x18002ab86  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002ab8b  mov     rax, [rax]
0x18002ab8e  lea     rcx, PKEY_Music_Conductor
0x18002ab95  mov     [rax+40h], rcx
0x18002ab99  lea     rcx, [rsp+68h+var_30]
0x18002ab9e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002aba3  lea     rdx, aDirector; "DIRECTOR"
0x18002abaa  lea     rcx, [rsp+68h+var_30]
0x18002abaf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002abb4  nop
0x18002abb5  lea     r8, [rsp+68h+var_30]
0x18002abba  lea     rdx, [rsp+68h+var_48]
0x18002abbf  mov     rcx, rbx
0x18002abc2  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002abc7  mov     rax, [rax]
0x18002abca  lea     rcx, PKEY_Video_Director
0x18002abd1  mov     [rax+40h], rcx
0x18002abd5  lea     rcx, [rsp+68h+var_30]
0x18002abda  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002abdf  lea     rdx, aAssistantDirec; "ASSISTANT_DIRECTOR"
0x18002abe6  lea     rcx, [rsp+68h+var_30]
0x18002abeb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002abf0  nop
0x18002abf1  lea     r8, [rsp+68h+var_30]
0x18002abf6  lea     rdx, [rsp+68h+var_48]
0x18002abfb  mov     rcx, rbx
0x18002abfe  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002ac03  mov     rax, [rax]
0x18002ac06  mov     [rax+40h], rdi
0x18002ac0a  lea     rcx, [rsp+68h+var_30]
0x18002ac0f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ac14  lea     rdx, aDirectorOfPhot; "DIRECTOR_OF_PHOTOGRAPHY"
0x18002ac1b  lea     rcx, [rsp+68h+var_30]
0x18002ac20  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002ac25  nop
0x18002ac26  lea     r8, [rsp+68h+var_30]
0x18002ac2b  lea     rdx, [rsp+68h+var_48]
0x18002ac30  mov     rcx, rbx
0x18002ac33  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002ac38  mov     rax, [rax]
0x18002ac3b  mov     [rax+40h], rdi
0x18002ac3f  lea     rcx, [rsp+68h+var_30]
0x18002ac44  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ac49  lea     rdx, aSoundEngineer; "SOUND_ENGINEER"
0x18002ac50  lea     rcx, [rsp+68h+var_30]
0x18002ac55  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002ac5a  nop
0x18002ac5b  lea     r8, [rsp+68h+var_30]
0x18002ac60  lea     rdx, [rsp+68h+var_48]
0x18002ac65  mov     rcx, rbx
0x18002ac68  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002ac6d  mov     rax, [rax]
0x18002ac70  mov     [rax+40h], rdi
0x18002ac74  lea     rcx, [rsp+68h+var_30]
0x18002ac79  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ac7e  lea     rdx, aArtDirector; "ART_DIRECTOR"
0x18002ac85  lea     rcx, [rsp+68h+var_30]
0x18002ac8a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002ac8f  nop
0x18002ac90  lea     r8, [rsp+68h+var_30]
0x18002ac95  lea     rdx, [rsp+68h+var_48]
0x18002ac9a  mov     rcx, rbx
0x18002ac9d  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002aca2  mov     rax, [rax]
0x18002aca5  mov     [rax+40h], rdi
0x18002aca9  lea     rcx, [rsp+68h+var_30]
0x18002acae  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002acb3  lea     rdx, aProductionDesi; "PRODUCTION_DESIGNER"
0x18002acba  lea     rcx, [rsp+68h+var_30]
0x18002acbf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002acc4  nop
0x18002acc5  lea     r8, [rsp+68h+var_30]
0x18002acca  lea     rdx, [rsp+68h+var_48]
0x18002accf  mov     rcx, rbx
0x18002acd2  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002acd7  mov     rax, [rax]
0x18002acda  mov     [rax+40h], rdi
0x18002acde  lea     rcx, [rsp+68h+var_30]
0x18002ace3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ace8  lea     rdx, aChoregrapher; "CHOREGRAPHER"
0x18002acef  lea     rcx, [rsp+68h+var_30]
0x18002acf4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002acf9  nop
0x18002acfa  lea     r8, [rsp+68h+var_30]
0x18002acff  lea     rdx, [rsp+68h+var_48]
0x18002ad04  mov     rcx, rbx
0x18002ad07  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002ad0c  mov     rax, [rax]
0x18002ad0f  mov     [rax+40h], rdi
0x18002ad13  lea     rcx, [rsp+68h+var_30]
0x18002ad18  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ad1d  lea     rdx, aCostumeDesigne; "COSTUME_DESIGNER"
0x18002ad24  lea     rcx, [rsp+68h+var_30]
0x18002ad29  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002ad2e  nop
0x18002ad2f  lea     r8, [rsp+68h+var_30]
0x18002ad34  lea     rdx, [rsp+68h+var_48]
0x18002ad39  mov     rcx, rbx
0x18002ad3c  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002ad41  mov     rax, [rax]
0x18002ad44  mov     [rax+40h], rdi
0x18002ad48  lea     rcx, [rsp+68h+var_30]
0x18002ad4d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ad52  lea     rdx, aActor; "ACTOR"
0x18002ad59  lea     rcx, [rsp+68h+var_30]
0x18002ad5e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002ad63  nop
0x18002ad64  lea     r8, [rsp+68h+var_30]
0x18002ad69  lea     rdx, [rsp+68h+var_48]
0x18002ad6e  mov     rcx, rbx
0x18002ad71  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002ad76  mov     rax, [rax]
0x18002ad79  mov     [rax+40h], rdi
0x18002ad7d  lea     rcx, [rsp+68h+var_30]
0x18002ad82  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ad87  lea     rdx, aCharacter; "CHARACTER"
0x18002ad8e  lea     rcx, [rsp+68h+var_30]
0x18002ad93  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002ad98  nop
0x18002ad99  lea     r8, [rsp+68h+var_30]
0x18002ad9e  lea     rdx, [rsp+68h+var_48]
0x18002ada3  mov     rcx, rbx
0x18002ada6  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002adab  mov     rax, [rax]
0x18002adae  mov     [rax+40h], rdi
0x18002adb2  lea     rcx, [rsp+68h+var_30]
0x18002adb7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002adbc  lea     rdx, aWrittenBy; "WRITTEN_BY"
0x18002adc3  lea     rcx, [rsp+68h+var_30]
0x18002adc8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002adcd  nop
0x18002adce  lea     r8, [rsp+68h+var_30]
0x18002add3  lea     rdx, [rsp+68h+var_48]
0x18002add8  mov     rcx, rbx
0x18002addb  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002ade0  mov     rax, [rax]
0x18002ade3  lea     rcx, PKEY_Media_Writer
0x18002adea  mov     [rax+40h], rcx
0x18002adee  lea     rcx, [rsp+68h+var_30]
0x18002adf3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002adf8  lea     rdx, aScreenplayBy; "SCREENPLAY_BY"
0x18002adff  lea     rcx, [rsp+68h+var_30]
0x18002ae04  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002ae09  nop
0x18002ae0a  lea     r8, [rsp+68h+var_30]
0x18002ae0f  lea     rdx, [rsp+68h+var_48]
0x18002ae14  mov     rcx, rbx
0x18002ae17  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002ae1c  mov     rax, [rax]
0x18002ae1f  mov     [rax+40h], rdi
0x18002ae23  lea     rcx, [rsp+68h+var_30]
0x18002ae28  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ae2d  lea     rdx, aEditedBy; "EDITED_BY"
0x18002ae34  lea     rcx, [rsp+68h+var_30]
0x18002ae39  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002ae3e  nop
0x18002ae3f  lea     r8, [rsp+68h+var_30]
0x18002ae44  lea     rdx, [rsp+68h+var_48]
0x18002ae49  mov     rcx, rbx
0x18002ae4c  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002ae51  mov     rax, [rax]
0x18002ae54  mov     [rax+40h], rdi
0x18002ae58  lea     rcx, [rsp+68h+var_30]
0x18002ae5d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ae62  lea     rdx, aProducer; "PRODUCER"
0x18002ae69  lea     rcx, [rsp+68h+var_30]
0x18002ae6e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002ae73  nop
0x18002ae74  lea     r8, [rsp+68h+var_30]
0x18002ae79  lea     rdx, [rsp+68h+var_48]
0x18002ae7e  mov     rcx, rbx
0x18002ae81  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002ae86  mov     rax, [rax]
0x18002ae89  lea     rcx, PKEY_Media_Producer
0x18002ae90  mov     [rax+40h], rcx
0x18002ae94  lea     rcx, [rsp+68h+var_30]
0x18002ae99  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ae9e  lea     rdx, aCoproducer; "COPRODUCER"
0x18002aea5  lea     rcx, [rsp+68h+var_30]
0x18002aeaa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002aeaf  nop
0x18002aeb0  lea     r8, [rsp+68h+var_30]
0x18002aeb5  lea     rdx, [rsp+68h+var_48]
0x18002aeba  mov     rcx, rbx
0x18002aebd  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002aec2  mov     rax, [rax]
0x18002aec5  mov     [rax+40h], rdi
0x18002aec9  lea     rcx, [rsp+68h+var_30]
0x18002aece  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002aed3  lea     rdx, aExecutiveProdu; "EXECUTIVE_PRODUCER"
0x18002aeda  lea     rcx, [rsp+68h+var_30]
0x18002aedf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002aee4  nop
0x18002aee5  lea     r8, [rsp+68h+var_30]
0x18002aeea  lea     rdx, [rsp+68h+var_48]
0x18002aeef  mov     rcx, rbx
0x18002aef2  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
  ... truncated ...
```
